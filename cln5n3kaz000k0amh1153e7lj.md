---
title: "🚀📅 Day 52 DevOps Challenge - Terraform Variables and Data Types: A Comprehensive Guide"
datePublished: Sat Sep 30 2023 06:16:08 GMT+0000 (Coordinated Universal Time)
cuid: cln5n3kaz000k0amh1153e7lj
slug: day-52-devops-challenge-terraform-variables-and-data-types-a-comprehensive-guide
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1695975167588/bac0d0b1-bfde-43e0-b28d-94afd459b28c.png
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1696054554596/61b9d6b6-a139-4ca5-9168-3d9b10d8b5e2.png
tags: aws, web-development, devops, 2articles1week, 90daysofdevops

---

Terraform, an infrastructure as a code tool, allows you to manage and provision your infrastructure using declarative configuration files. Variables are a crucial aspect of Terraform configuration, enabling you to define dynamic values and enhance the flexibility of your infrastructure setups. In this guide, we'll delve into Terraform variables and data types, showcasing their importance and demonstrating practical usage. 🚀

## **Terraform Variables: Harnessing Flexibility 🎛️**

Variables in Terraform serve as containers for holding various values, such as instance names, configurations, or any data that needs to be dynamic within your infrastructure. Utilizing variables enhances the reusability, maintainability, and adaptability of your Terraform configurations.

To set up variables, we commonly use a [`variables.tf`](http://variables.tf) file within our Terraform project to centralize and organize them effectively. Let's consider an example where we define two variables, "filename" and "content":

```bash
# variables.tf

variable "filename" {
  default = "/home/adarsh/Devops/Terraform-AV-YT/terr/demo-var.txt"
}

variable "content" {
  default = "This is coming from a variable which was updated"
}
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1695973928772/61535f31-1c72-4bc5-98c3-a5db1c17ab88.png align="center")

In the example above, we've defined two variables: "filename" and "content" with their respective default values. 📄

## **Accessing Variables in Terraform Configuration 🏗️**

To access these variables in your main configuration ([`main.tf`](http://main.tf)), you utilize the `var` object. Let's illustrate this by creating a local file using Terraform and utilizing the defined variables:

### **Task-01: Creating a Local File 📝**

```bash
# main.tf

resource "local_file" "devops" {
  filename = var.filename
  content  = var.content
}
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1695974111327/a8d30322-f8ba-49f5-8923-316d8a1f31d4.png align="center")

In this task, we've used the `var.filename` and `var.content` variables to set the filename and content of a local file resource. This demonstrates how variables seamlessly integrate into your Terraform configurations.

After defining the variables in [`variables.tf`](http://variables.tf) and utilizing them in [`main.tf`](http://main.tf) to create a local file, let's proceed with Terraform commands to initialize, plan, and apply the configuration.

```bash
terraform init
terraform plan
terraform apply
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1695974640577/e36ab775-396d-4225-b1e9-90df4e43b441.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1695974664524/fab7cdf0-a819-420a-aa81-5b2379379c85.png align="center")

Terraform will execute the plan and create the local file with the specified filename and content.

Check if the file was created and the content matches the specified values.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1695974721648/b4488112-4c7f-4261-97ca-4ad6c2e2e4cc.png align="center")

### **Task-02 📋**✔️**Terraform Data Types: Enhancing Versatility 📊**

Terraform supports various data types, each serving unique purposes and use cases. Let's explore some of these data types and how to effectively utilize them within your configurations.

### **Map Data Type:**

```bash
# variables.tf

variable "file_contents" {
  type    = map
  default = {
    "statement1" = "this is cool"
    "statement2" = "this is cooler"
  }
}
```

In this, we demonstrate the usage of the Map data type. Here, we define a variable "file\_contents" as a map containing key-value pairs representing statements. This data type is useful for organizing related data with meaningful labels.

### **List, Set, and Object Data Types:**

To demonstrate the usage of List, Set, and Object data types, we'll create separate examples showcasing each type.

**List:**

```bash
variable "example_list" {
  type    = list
  default = ["item1", "item2", "item3"]
}

output "list_output" {
  value = var.example_list
}
```

**Set:**

```bash
variable "example_set" {
  type    = set(string)
  default = toset(["item1", "item2", "item3"])
}

output "set_output" {
  value = var.example_set
}
```

**Object:**

```bash
variable "example_object" {
  type = object({
    key1 = string
    key2 = string
  })
  default = {
    key1 = "value1"
    key2 = "value2"
  }
}

output "object_output" {
  value = var.example_object
}
```

In Task-02, we showcase the usage of List, Set, and Object data types. These data types provide versatility and structure, enabling effective organization and manipulation of data within your Terraform configurations. 🧩

### **Refreshing Terraform State 🔄**

To refresh the Terraform state based on your configuration file and reload variables, you can use the `terraform refresh` command. This command ensures that the state accurately reflects the resources managed by your configuration, incorporating any changes made to variables or configurations.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1695974826402/3cc159d3-d522-4d44-a0c7-deb4e02892f7.png align="center")

By understanding and effectively utilizing Terraform variables and data types, you enhance your ability to create flexible, maintainable, and robust infrastructure configurations.

Happy Terraforming! 🌍