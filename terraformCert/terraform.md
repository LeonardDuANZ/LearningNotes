# Terraform
## IaC
Manage infrastructure using code. Stored in source control. Declarative and Imperative. Idempotent and consistent.

Idempotent: terraform apply to create some resources already done before, they will not be create again.

Consistent: terraform using .tfstate file to store, track and manage the states of every resource.

- Declartive:
    ```
    food taco "bean-taco" {
        ingredients = ["beans", "cheese", "lettuce", "salsa"]
    }
    ```
- Imperative:
    ``` 
    # make a taco
    get shell
    get beans
    get cheese
    get letture
    get salsa

    put beans in shell
    put cheese on beans
    put lettuce
    ...
    ```

benefits: reusable components, automate deployment, repeatable process, consistent environment, documented architecture.


