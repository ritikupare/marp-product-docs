---
marp: true
theme: custom
paginate: true
---

<!--
This is a Marp presentation for product documentation.
Custom theme, page numbers, background image, math, and directives included.
-->

<style>
/* Custom theme: "custom" */
section.marp-theme-custom {
  background: radial-gradient(circle at top left, #0f172a, #020617);
  color: #e5e7eb;
  font-family: system-ui, -apple-system, BlinkMacSystemFont, "Segoe UI", sans-serif;
  padding: 3rem;
}

/* Headings */
section.marp-theme-custom h1,
section.marp-theme-custom h2,
section.marp-theme-custom h3 {
  color: #38bdf8;
}

/* Page numbers (bottom-right) */
section.marp-theme-custom::after {
  content: attr(data-marpit-pagination) " / " attr(data-marpit-pagination-total);
  position: absolute;
  bottom: 1.5rem;
  right: 2rem;
  font-size: 0.7rem;
  opacity: 0.7;
  letter-spacing: 0.08em;
}

/* Lead slide style */
section.marp-theme-custom.lead {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: flex-start;
  font-size: 1.2rem;
}
</style>

# Product X Documentation

**Technical Overview & Architecture**

Contact: **24f2008723@ds.study.iitm.ac.in**

---

<!-- _class: lead -->

## Why Marp for Product Docs?

- Markdown-based → easy to maintain in Git and review in pull requests
- Single source → export to **HTML, PDF, PPTX**
- Developer-friendly → works with editor plugins (VS Code, etc.)
- Great for **living documentation** that evolves with the product

---

<!-- _class: lead -->
<!-- _backgroundColor: #020617 -->

## Documentation Structure

1. Introduction & problem statement  
2. System architecture  
3. API design & data contracts  
4. Performance characteristics & complexity  
5. Deployment & monitoring

> This slide uses a custom class via Marp directive  
> `<!-- _class: lead -->` and a custom `_backgroundColor`.

---

<!-- _class: lead -->

![bg](https://images.pexels.com/photos/1181675/pexels-photo-1181675.jpeg)

# High-Level Architecture

- Client applications (web / mobile)
- API Gateway (rate limiting, auth)
- Core Service (business logic)
- Database and cache layer
- Observability (logs, metrics, traces)

_This slide demonstrates a **background image** using `![bg](...)`._

---

## Algorithmic Complexity

To process a batch of **n** items:

- A naive implementation scans all pairs  
  → time complexity: `$T(n) = O(n^2)$`

- Our optimized divide-and-conquer pipeline:

$$
T(n) = O(n \log n)
$$

- Memory usage remains linear:

$$
S(n) = O(n)
$$

These equations are rendered by Marp using math support (KaTeX/MathJax depending on the toolchain).

---

## API Rate Limiting Example

We define a fixed-window limiter:

- Window size: \( \Delta t = 60 \, \text{seconds} \)
- Max requests per user: \( R_{\max} = 120 \)

Allowed if:

$$
\text{requests\_in\_window}(user) \le R_{\max}
$$

This can be extended to **token-bucket** or **leaky-bucket** algorithms as the system scales.

---

## Deployment & Version Control Workflow

1. Write docs in `product-docs.md`
2. Commit changes in a feature branch
3. Open **pull request** for review
4. CI pipeline renders slides to **PDF** and **HTML**
5. Merge into `main` → publish docs to internal portal

Using Markdown + Marp keeps documentation **close to the code**.

---

# Thank You

For questions or feedback, reach out at:

**24f2008723@ds.study.iitm.ac.in**

_Product documentation maintained as code, powered by Marp._
