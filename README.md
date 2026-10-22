# Multi-Agent AI System for Cognitive Digital Twins in Education

A proposed personalized learning platform in which AI agents build a **subject knowledge graph** and teach using a continuously updated **learner cognitive digital twin**.

## Knowledge model

- **E:** The full scoped subject, represented as a graph of concepts and subconcepts with weighted, annotated relationships, layers, and node states.
- **F:** The learner's actual, evolving understanding (not directly observable).
- **F′:** A graph-based **cognitive digital twin** estimating F, aligned with E and updated from learner evidence.

## How it works

1. The user logs in, selects an existing subject or introduces a new one, and defines its scope.
2. A **research agent** gathers web material and constructs E.
3. Diagnostic questions initialize F′.
4. A **tutoring agent** repeatedly **plans a lesson from E and F′ → predicts the learner's response → teaches and quizzes → observes answers, hypotheses, questions, and observations → compares prediction with reality → updates F′ → plans the next lesson**.

## Conceptual mathematical model

$$
L_{t+1}=\pi(E,F'_t),\qquad \widehat{O}_{t+1}=P(F'_t,L_{t+1})
$$
$$
\varepsilon_{t+1}=d(\widehat{O}_{t+1},O_{t+1}),\qquad F'_{t+1}=U(F'_t,O_{t+1},\varepsilon_{t+1})
$$
$$
\text{Learning goal: }\min_{\text{adaptive lessons}} D(F'_t,E)
$$

Here, O is observed learner output. **Teaching reduces the gap to E; observation-driven updates keep F′ faithful to F.** The functions and distance measures are conceptual, not predefined algorithms.

## Required technologies and frameworks

Spring · JPA · Servlet · REST · gRPC · Asynchronous communication · Logback · Unit tests · Integration tests · Circuit breaking & retries · Kong · Eclipse Ditto · Vert.x · [NARU](https://github.com/thevpc/naru) · [Pyramid Architecture](https://github.com/thevpc/the-pyramid-architecture) · [Nuts](https://github.com/thevpc/nuts)
