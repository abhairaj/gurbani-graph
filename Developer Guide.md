

# 📘 **Gurbani Graph Naming Guide**

*A shared standard for identifiers, filenames, and IRIs*

This guide defines how to name **Shabd nodes**, **Tuk nodes**, **GlossUnit nodes**, and related TTL files in the Gurbani Graph project. It ensures consistency across contributors and makes the graph predictable, searchable, and maintainable.

---

# 1. 📚 Scripture Codes

Each scripture is represented by a short, lowercase identifier:

| Scripture                  | Code   |
| -------------------------- | ------ |
| Sri Guru Granth Sahib      | `sggs` |
| (Future) Dasam Granth      | `dg`   |
| (Future) Bhai Gurdas Varan | `bgv`  |
| (Future) Bhai Nand Lal     | `bnl`  |

**All IRIs begin with the scripture code.**

---

# 2. 🧩 **Shabd Identifier Pattern**

## **Format:**

```
{scripture_code}_ang{ang_number}_{short_shabd_code}
```

### ✔️ Examples

```
sggs_ang705_aad_pooran
sggs_ang1_japji_pauri1
sggs_ang8_asa_diwaraan_sthiraag
```

## **Rules**

1. **scripture_code**
   As listed above (`sggs` for now).

2. **ang_number**

   * The Ang where the shabd *begins*.
   * Always integer; no zero padding.

3. **short_shabd_code**

   * A short, meaningful, lowercase snake_case code based on:

     * common colloquial name (preferred if available)
     * or a distinctive phrase from the opening or signature line
   * Keep it short: 1–3 words
   * Avoid long Gurmukhi transliterations
   * Avoid diacritics; ASCII only

### ❗ Colloquial Priority Rule

If Sikhs commonly refer to the shabd by a known name (e.g., “Aad Pooran,” “Man Re,” “So Dar”), **use that as the short code**.

---

# 3. ✒️ **Tuk Identifier Pattern**

Tuk identifiers must be *rooted under the shabd ID*.

## **Format:**

```
{shabd_id}_tuk{index}
```

### ✔️ Example

If the shabd is:

```
sggs_ang705_aad_pooran
```

Then tuks become:

```
sggs_ang705_aad_pooran_tuk1
sggs_ang705_aad_pooran_tuk2
sggs_ang705_aad_pooran_tuk3
...
```

## **Rules**

* Tuk index is **relative to the shabd**, not to the Ang.
* Always numbered sequentially from 1.
* Even if the shabd spans multiple Angs, *do not change the prefix*.

---

# 4. 🧱 **GlossUnit Identifier Pattern**

GlossUnits are the semantic atoms inside each Tuk.

## **Format:**

```
{tuk_id}_gu{index}
```

### ✔️ Example

```
sggs_ang705_aad_pooran_tuk4_gu1
sggs_ang705_aad_pooran_tuk4_gu2
```

## **Rules**

* GlossUnits must reflect **semantically meaningful phrases**, not grammatical tokens.
* Index within each Tuk starts from 1.

---

# 5. 📄 **TTL Filename Rule**

TTL filename matches the shabd identifier:

### **Format**

```
{shabd_id}.ttl
```

### ✔️ Example

```
sggs_ang705_aad_pooran.ttl
```

---

# 6. 🎨 **Theme Naming Rules**

Themes are lowerCamelCase (not snake_case), e.g.:

```
DivinePervasion
ContemplativeRemembrance
DevotionalLove
TranscendenceImmanence
```

### Rules:

* Themes should be conceptual categories.
* New themes are permitted when:

  * multiple shabds express a similar idea
  * or when a new theme clarifies graph queries
* Theme names should never depend on scripture structure (i.e., not “JapjiThemes”).

---

# 7. 🔧 **Resource Naming Summary**

| Entity        | Pattern                       |
| ------------- | ----------------------------- |
| **Shabd**     | `{scripture}_ang{ang}_{code}` |
| **Tuk**       | `{shabd_id}_tuk{n}`           |
| **GlossUnit** | `{tuk_id}_gu{n}`              |
| **TTL File**  | `{shabd_id}.ttl`              |
| **Theme**     | `CamelCaseConcept`            |

---

# 8. 🌟 Examples (Full Path)

### **Shabd:**

```
sggs_ang705_aad_pooran
```

### **Tuks:**

```
sggs_ang705_aad_pooran_tuk1
sggs_ang705_aad_pooran_tuk2
sggs_ang705_aad_pooran_tuk3
...
```

### **GlossUnits:**

```
sggs_ang705_aad_pooran_tuk3_gu1
sggs_ang705_aad_pooran_tuk3_gu2
```

### **File:**

```
ang705_aad_pooran.ttl
```

---

# 9. Git Repo Structure

```
/ttl/
    ontology.ttl
    reference.ttl
    themes.ttl
    /shabds/
        sggs/
            ang705_aad_pooran.ttl
            japji_pauri1.ttl
```
