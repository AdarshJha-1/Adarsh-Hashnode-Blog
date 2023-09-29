---
title: "🚀📅 Day 15 DevOps Challenge -🐍📚Python Libraries for DevOps:  Streamlining JSON and YAML Handling with Ease 🚀"
seoTitle: "JSON-YAML-Python: DevOps Efficiency Boost 🚀"
seoDescription: "JSON-YAML-Python: DevOps Efficiency Boost 🚀"
datePublished: Tue Aug 15 2023 05:31:14 GMT+0000 (Coordinated Universal Time)
cuid: cllbv8nbq000n08job46g245j
slug: day-15-devops-challenge-devops-json-yaml-python-efficiency
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1692077250930/03f263a4-74ae-4d3b-80f4-73c937315c33.png
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1692077419912/65f48790-3bf0-4298-a558-97c061a2584d.png
tags: software-development, python, web-development, devops, 90daysofdevops

---

## JSON and YAML: The DevOps Engineer's Data Formats 📄

Before we explore the Python libraries that make JSON and YAML file handling a breeze, let's quickly revisit these essential data formats. 📝

**JSON (JavaScript Object Notation):** JSON is a lightweight data interchange format that's easy for humans to read and write, and it's also easy for machines to parse and generate. It's widely used for configuration files, API responses, and data storage.

**YAML (YAML Ain't Markup Language):** YAML is a human-readable data serialization format often used for configuration files and data exchange between languages with different data structures. Its indentation-based syntax makes it easy to read and write, and it's commonly seen in DevOps workflows.

## Python Libraries for Effortless File Parsing 📂

### **1\.** `json` Library 📜

The `json` library is a built-in Python module that provides methods to work with JSON data. It offers functions to encode Python objects into JSON strings and decode JSON strings into Python objects. DevOps Engineers can use this library to seamlessly parse and manipulate JSON files.

Example Usage:

```python
import json

# Reading JSON from a file
with open('data.json') as json_file:
    data = json.load(json_file)

# Working with JSON data
print(data['key'])
```

### **2\.** `pyyaml` Library 🧀

For handling YAML files, the `pyyaml` library is a go-to choice. It allows you to effortlessly load YAML data into Python objects and vice versa. With its user-friendly interface, DevOps Engineers can easily incorporate YAML configuration files into their automation scripts.

Example Usage:

```python
import yaml

# Reading YAML from a file
with open('config.yaml') as yaml_file:
    data = yaml.safe_load(yaml_file)

# Working with YAML data
print(data['key'])
```

## Streamlining DevOps Tasks with Python Libraries 🛠️

DevOps Engineers rely on various Python libraries, including the ones mentioned above, to streamline their daily tasks. These libraries enable you to read, parse, and manipulate JSON and YAML files effortlessly. From automating server configurations to orchestrating cloud resources, Python libraries are your allies in the world of DevOps. 💪🤖

### **Task-1:** Creating a Dictionary in Python and Writing it to a JSON File📄🔍.

```python
pythonCopy codeimport json

# Create a dictionary
data = {
    "name": "Adarsh Jha",
    "age": 18,
    "city": "New-Delhi"
}

# Specify the file name
file_name = "data.json"

# Write the dictionary to a JSON file
with open(file_name, 'w') as json_file:
    json.dump(data, json_file)

print(f"Dictionary written to {file_name}")
```

In this example, we import the `json` module, create a dictionary named `data`, and then use the `json.dump()` function to write the dictionary to a JSON file named "data.json". The file is opened in write mode (`'w'`), and the `json.dump()` function takes care of converting the dictionary into JSON format and writing it to the file. Finally, we print a message to confirm that the dictionary has been written to the file.

After running the script, you'll see a file named `data.json` in the same directory as your Python script. The contents of the JSON file will be:

```python
{"name": "Adarsh Jha", "age": 18, "city": "New-Delhi"}
```

### **Task-2:** 📄🔍 Reading "services.json" and 🖨️ Printing Cloud Service Provider Names.

1. Create a JSON file named `services.json` and populate it with the following content:
    

```json
{
  "cloud_services": [
    { "provider": "aws", "service": "ec2" },
    { "provider": "azure", "service": "VM" },
    { "provider": "gcp", "service": "compute engine" }
  ]
}
```

1. Create a Python script named `cloud_services.py` in the same directory as your `services.json` file. Add the following code to the script:
    

```python
import json

# Load data from JSON file
with open('services.json') as json_file:
    data = json.load(json_file)

# Print the service names of every cloud service provider
for item in data['cloud_services']:
    print(f"{item['provider']} : {item['service']}")
```

1. Run the Python script `cloud_services.py` using your Python interpreter. This script will read the `services.json` file and print the desired output:
    

```python
aws : ec2
azure : VM
gcp : compute engine
```

Make sure that both the `services.json` file and the `cloud_services.py` script is in the same directory when you run the script. This should produce the desired output as you mentioned earlier.

### **Task-3:** 📝🐍 Reading "services.yaml" with Python and Converting YAML to JSON.

To read a YAML file using Python and convert its contents to JSON, you can use the `pyyaml` library to parse the YAML and the `json` library to convert it to JSON format. Make sure you have both libraries installed by running:

```python
pip install pyyaml
```

Here's an example code snippet to achieve this:

```python
import yaml
import json

# Read YAML file
yaml_file_path = "services.yaml"

with open(yaml_file_path, "r") as yaml_file:
    yaml_data = yaml.safe_load(yaml_file)

# Convert YAML to JSON
json_data = json.dumps(yaml_data, indent=4)

# Print or save the JSON data as needed
print(json_data)

# If you want to save the JSON data to a file
json_file_path = "services.json"
with open(json_file_path, "w") as json_file:
    json_file.write(json_data)

print(f"YAML data from '{yaml_file_path}' has been converted and saved to '{json_file_path}'.")
```

Replace `"services.yaml"` with the actual path to your YAML file. This code reads the YAML file, parses its contents, converts it to JSON, and either prints the JSON data or saves it to a JSON file.

Remember to adjust the file paths as needed to match your directory structure and file names.

**In conclusion, JSON and YAML serve as vital tools for DevOps tasks 🛠️. Python's json and pyyaml libraries provide seamless file handling capabilities 📂, empowering engineers to efficiently manage data interchange and configurations. By harnessing these libraries, DevOps professionals can optimize processes**