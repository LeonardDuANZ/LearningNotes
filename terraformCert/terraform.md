# Terraform
## IaC
Manage infrastructure using code. Stored in source control. Declarative and Imperative. Idempotent and consistent.

Idempotent: terraform apply to create some resources already done before, they will not be create again.

Consistent: terraform using .tfstate file to store, track and manage the states of every resource.

- Declarative:
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
    get lettuce
    get salsa

    put beans in shell
    put cheese on beans
    put lettuce
    ...
    ```

benefits: reusable components, automate deployment, repeatable process, consistent environment, documented architecture.

## Code
Three parts: provider, data, resource

format: 
* to new a resource ```resource <resource_type> <recource_name_label>```
* to call a resource <resource_type>.<name_label>.<attribute>

workflow: init, plan, apply
check code: format: terraform fmf; logic: terraform validate

### Variables
* input variable (variables.tf)
    * format:
    ```
    variable "name_label"{
        type = value
        description = "it is a string"
        default = value
        sensitive = true | false # default: false
    }
    ```
    * using variable: var.<name_label>
    * primitive(string, number, bool); collection(list, set, map); structural(tuple, object); any(list(any)); Null(default one)

* local values (locals.tf)
    * format
    ```
    locals {
        "name1": "value1"
        "name2": "value2"
        "name3": "value3"
    }
    ```
    * using variable: local.<key>
* outputs (outputs.tf)
    * format:
    ```
    output "name_label"{
        value = value
        description = "it is a string"
        sensitive = true | false # default: false
    }
    ```

variables running rank (the last one wins): 
1. TF_VAR_ environment variable
2. terraform.tfvars or terraform.tfvars.json
3. .auto.tfvars or .auto.tfvars.json
4. -var-file flag
5. -var flag :-var="name"=value
6. command line prompt

### state commands
* terraform state list
* terraform state show ADDRESS
* terraform state mv SOURCE DESTINATION
* terraform state rm ADDRESS
