# Decision Matrix: Team Size vs. Architecture Choice

This matrix helps determine when to transition from a monolith to a layered or service-oriented architecture based on team size and complexity.

| Team Size       | Architecture Choice                       | Pros                                                                 | Cons                                                                 |
|-----------------|-------------------------------------------|----------------------------------------------------------------------|----------------------------------------------------------------------|
| **< 10**        | Monolith                                  | - Simple to develop and deploy<br>- Minimal coordination overhead   | - Can become tightly coupled as it grows<br>- Harder to scale parts independently |
| **10–40**       | Monolith with Modular Boundaries          | - Easier to maintain separation of concerns<br>- Still simple deployments | - Requires discipline to maintain boundaries<br>- Still one deployable unit |
| **40–100**      | Modular Monolith / Layered Architecture   | - Clear domain boundaries<br>- Enables parallel development by multiple teams | - More complex deployment pipeline<br>- Requires governance and clear contracts |
| **100+**        | Layered Architecture / Microservices      | - Independent scaling and deployment<br>- Aligns with larger org structures | - Higher operational overhead<br>- Requires robust DevOps & monitoring |

---

## Key Considerations for Stakeholders

1. **Coordination Overhead** – As team size grows, merge conflicts, blocking dependencies, and review bottlenecks increase.
2. **Change Risk** – In monoliths, small changes can require retesting the entire system.
3. **Scaling Requirements** – If parts of the system need different scaling strategies, modular or service-oriented approaches work better.
4. **Product Diversity** – Multiple products sharing the same core logic benefit from separation into layers or services.
5. **Onboarding Time** – Large, tightly coupled systems slow down new developer onboarding.

---

**Rule of Thumb:**  
- Keep it monolithic for small teams focused on rapid delivery.  
- Modularize as soon as coordination and complexity start affecting velocity.  
- Move to layered or service-oriented architecture when multiple teams must work independently at scale.
