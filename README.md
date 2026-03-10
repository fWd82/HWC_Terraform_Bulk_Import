# HuaweiCloud Terraform Importer

A simple, web-based tool to bulk generate Terraform HCL `import` blocks from HuaweiCloud RMS (Resource Management Service) API responses. This tool helps automate the process of bringing existing HuaweiCloud resources under Terraform management.

## 🌐 Try it Online

You can access the hosted version of this tool here:  
**[HuaweiCloud Terraform Importer](https://fawadiqbal.com/tools/Terraform_HWC_Importer/)**

## 💡 Use Case: Environment Replication

This project is particularly valuable when you have an environment (e.g., Development) that was manually created via the console and you need to replicate it for a new environment (e.g., Staging). 

By using this tool, you can:
1.  **Import** all existing resources from your console-created environment into your Terraform state.
2.  **Generate** the corresponding Terraform HCL code automatically.
3.  **Clone** the environment by simply updating resource names and configurations, allowing you to spin up a matching Staging environment in minutes.

## 🚀 Key Features

- **Bulk Generation**: Process multiple resources at once from a single API response.
- **Resource Selection**: Choose exactly which resources you want to import using built-in filters for regions and providers.
- **Automatic Mapping**: Uses a precise mapping database to match HuaweiCloud RMS resource types to their Terraform resource equivalents.
- **Modern UI**: Dark-themed, responsive interface with smooth animations and interactive resource explorer.
- **Secure & Private**: Data is processed entirely in your browser; no cloud data or API responses are ever sent to a server.

## 💻 Tech Stack & Local Usage

The tool is built using pure **HTML5, CSS3 (Vanilla), and Modern JavaScript**. It has zero dependencies and requires no build steps.

### Running Locally
1.  **Clone** the repository.
2.  **Open** `index.html` in any modern web browser.
3.  Ensure `huaweicloud_rms_tf_mapping.json` remains in the same directory to allow the tool to load the resource mappings.

## 🛠️ How to Use

1.  **Get Resource Data**:
    - Go to the [HuaweiCloud API Explorer](https://console-intl.huaweicloud.com/apiexplorer/#/openapi/RMS/debug?api=ListAllResources).
    - Authenticate and call the `ListAllResources` API.
    - Copy the full JSON response body.
2.  **Import to Tool**:
    - Open `index.html` in your browser.
    - Paste the JSON response into the textarea **or** upload the saved `.json` file.
    - Click **"Parse Resources"**.
3.  **Select & Generate**:
    - Review the list of detected resources.
    - Select the resources you want to import.
    - Click **"Generate Import Blocks"**.
4.  **Use in Terraform**:
    - Copy the generated HCL code.
    - Paste it into your Terraform configuration.
    - Run `terraform plan` to see the import plan.

## 📂 Project Structure

- `index.html`: The main web application.
- `huaweicloud_rms_tf_mapping.json`: The mapping database between RMS types and Terraform resources.
- `LICENSE`: Apache License 2.0.

## 🤝 Contributing

Contributions are welcome! If you find a missing mapping or have a feature request, feel free to open an issue or submit a pull request.

## 📄 License

This project is licensed under the Apache License 2.0 - see the [LICENSE](LICENSE) file for details.