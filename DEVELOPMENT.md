# Development Guide

This guide covers development standards for working with A11yhood. It currently focuses only on the frontend, the backend is still a TODO item. Testing and data model information also still needs to be added. If you haven't set up your local environment yet, start with the [Setup Guide](./docs/setup/SETUP.md).

---

## Table of Contents

- [Frontend Guidelines](#frontend-guidelines)
  - [Accessibility and Semantic HTML](#accessibility-and-semantic-html)
---

## Frontend Guidelines

The frontend is a React project written in TypeScript. The guiding principle for contributions is to **follow existing patterns and minimize duplicate code** — before adding a new utility, component, or type, check whether something already exists that can be reused or extended. 

Please note that this project is currently based on legacy code, including AI generated code. We are still working as a team to identify the resulting inefficiencies and reduce them. 


### Accessibility and Semantic HTML

Accessibility is a core value of this project, and the interface must reflect that commitment. All frontend contributions are expected to follow these conventions:

**Use semantic HTML.** Prefer native HTML elements that carry meaning over generic containers. Use `<button>` for actions, `<nav>` for navigation, `<main>` for primary content, `<section>` and `<article>` to organize content, and heading elements (`<h1>`–`<h6>`) in correct hierarchical order.
For `<section>` use the Section compontent.

**Do not use `div` or `span` where a semantic element exists.** If an element is clickable, it should be a `<button>` or `<a>` — not a `<div>` with an `onClick`. This ensures keyboard accessibility and correct screen reader behavior.

**Use ARIA only when native HTML is not sufficient.** Correct semantic HTML reduces or eliminates the need for ARIA. Add ARIA attributes only when there is no native HTML equivalent for the role or state you need to communicate.

**Ensure keyboard accessibility.** All interactive elements must be reachable and operable via keyboard. Do not remove or suppress focus styles.

**Do not rely on color alone to convey meaning.** Any information communicated through color must also be communicated through text or another visual indicator.

