**CI/CD Pipelines:**
[MS DOCS - CI vs CD ](https://learn.microsoft.com/en-us/azure/devops/pipelines/get-started/pipelines-get-started?view=azure-devops#automate-tests-builds-and-delivery)

**Definition:**

**CI (Continuous Integration)**: CI is a software development practice where code changes are frequently integrated into a shared repository. Each integration triggers automated tests to detect and fix issues early in the development process.

**CD (Continuous Delivery/Continuous Deployment)**: CD extends CI by automating the delivery and deployment of tested code to production or staging environments. Continuous Delivery focuses on making sure code is always in a deployable state, while Continuous Deployment takes it a step further by automatically deploying code changes to production when they pass all tests.

**In Easy Language:**

**CI (Continuous Integration)**: Think of CI like a kitchen where multiple chefs are preparing different parts of a meal. As soon as one chef finishes their part, it's placed on a shared table for others to use. This ensures that all ingredients and dishes are continuously integrated, and if something goes wrong, it's spotted quickly and fixed. In software, it means that as developers write code, it's regularly checked to make sure it still works with the rest of the code.

**CD (Continuous Delivery/Continuous Deployment)**: Imagine the kitchen again. In Continuous Delivery, the completed meal is ready on the shared table, and the head chef decides when to serve it to the customers. They can choose to serve it immediately or wait for the right moment. In software, Continuous Delivery means that the code is always ready for deployment, but the decision to actually put it into production is manual. 

In Continuous Deployment, the kitchen automatically serves the meal to customers as soon as it's ready, without the head chef's intervention. In software, Continuous Deployment means that code changes are automatically deployed to production once they pass all tests, without any manual steps.

**Key Differences:**

1. **Focus**:
   - CI focuses on frequent code integration and automated testing.
   - CD focuses on automating the delivery and deployment process.

2. **Deployment**:
   - CI doesn't involve deployment to production; it's about code integration and testing.
   - CD includes the deployment aspect, with Continuous Delivery stopping at the readiness stage and Continuous Deployment automatically deploying code changes to production.

3. **Manual vs. Automatic**:
   - In CI and Continuous Delivery, deployment decisions are manual, with someone deciding when to move code to production.
   - In Continuous Deployment, deployment is automatic when code passes all tests.

4. **Purpose**:
   - CI catches integration issues early and ensures code works together.
   - CD ensures that code is always in a deployable state, making the process more efficient and reliable.

5. **Role in SDLC (Software Development Life Cycle)**:
   - CI plays a crucial role in the development phase, ensuring that code is continuously integrated and tested during development.
   - CD spans the later stages of the SDLC, from integration and testing to delivery and deployment, ensuring that code is ready for production and, in the case of Continuous Deployment, automatically deploying it.

In summary, CI/CD pipelines are like a well-organized kitchen where chefs continuously prepare, test, and serve meals (code changes) to customers (production). CI focuses on cooking and testing, while CD manages when and how the meals are served, with Continuous Deployment being the most automatic and efficient option.


# Azure Pipelines
- Azure Pipelines automatically builds and tests code projects. It supports all major languages and project types and combines continuous integration, continuous delivery, and continuous testing to build, test, and deliver your code to any destination
## Need to get Started
To use Azure Pipelines, complete the following tasks:

Have an organization in Azure DevOps. If you don't have one, create an organization now.
Store your source code in a version control system.![image](https://github.com/Ananyojha/az-400/assets/76782360/b5d53707-6ca8-4907-9db8-43ea45e9774d)
