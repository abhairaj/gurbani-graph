# ✅ How to Ask for Ontology-Exact TTL Output

Whenever you want me to generate RDF/Turtle that conforms *exactly* to the **Gurbani Graph Ontology**, you can use any of the following prompt patterns.

---

## **1. Strict Mode (Recommended)**

**Use this phrase:**

> **“Please generate TTL normalized to the Gurbani Graph ontology exactly, with no deviations or new predicates.”**

---

## **2. Strict Mode with Input JSON**

> **“Normalize the following JSON into TTL using the Gurbani Graph ontology exactly as defined. Use only ontology classes and properties.”**

---

## **3. Strict Mode with Validation Constraint**

> **“Produce TTL that conforms 1:1 to the Gurbani Graph ontology: only existing classes, properties, ranges, and domains. No invented fields.”**

---

## **4. Strict Mode for Full Shabds or Pauris**

> **“Convert this entire shabd into TTL using the Gurbani Graph ontology exactly. Each line must be modeled as a `shabd:Line` with all required predicates.”**

---

## **5. Strict Structural Rule**

> **“Respond ONLY with valid TTL. Use only ontology prefixes and follow all domain/range constraints.”**

---

# ⚡ Shortcut Command

If you want a compact reusable trigger:

> **“Please output in GGO-TTL format.”**

(GGO = **Gurbani Graph Ontology**)

This will instantly switch me into strict ontology-compliant TTL generation mode.

---

# 🔧 Optional: Even More Rigor

If you want automated validation of every future TTL file, just ask:

> **“Please generate a SHACL validation profile for the Gurbani Graph ontology.”**

I can then check conformance mentally before responding.

---

# 📌 Summary

When you include any of the above instructions, I will:

* Use **only** ontology-defined classes
* Use **only** ontology-defined predicates
* Enforce **domain/range rules**
* Avoid inventing new properties
* Ensure IDs follow your naming pattern (`sggs:ang###_shabd##_line#`)
* Produce **valid, clean TTL only**

---

If you'd like, I can also prepare:

* A ready-to-paste **“developer note”** you can store in your project repo
* A **VS Code snippet** to automate prompting
* A **Gurbani Graph CLI prompt template**

Just let me know.
