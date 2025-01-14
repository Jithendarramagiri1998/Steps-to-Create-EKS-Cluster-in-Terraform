# Steps to Create EKS Cluster Using Terraform

## Prerequisites

1. **Install AWS CLI**
   - Download and install AWS CLI from the official [AWS CLI Documentation](https://docs.aws.amazon.com/cli/latest/userguide/install-cliv2.html).
   - Configure AWS CLI with your credentials:
     ```bash
     aws configure
     ```

2. **Install Terraform**
   - Download and install Terraform from the official [Terraform Website](https://developer.hashicorp.com/terraform/downloads).
   - Verify installation:
     ```bash
     terraform --version
     ```

---

## Structuring the Terraform Files

Follow a modular approach by dividing resources into reusable modules and specific files:

- **main.tf**: High-level orchestration.
- **variables.tf**: Define input variables.
- **outputs.tf**: Define outputs for resources.
- **Modules**: Create separate modules for VPC, EKS, etc.

---

## Using Modules to Manage Resources

- **Official Modules**: Use modules from the [Terraform Registry](https://registry.terraform.io/).
  - Example: For VPC or EKS, use official modules if available.
- **Custom Modules**: If no suitable module exists, create custom modules for reusability.
- Always define module sources and versions for consistency and compatibility.

---

## Best Practices

1. Avoid hardcoding sensitive values (e.g., access keys). Use **variables.tf**.
2. Use **outputs.tf** to programmatically fetch resource information.
3. Test the infrastructure using `terraform plan` before applying changes.

---

## Execution Steps

1. **Initialize Terraform**
   ```bash
   terraform init
   ```

2. **Validate the Configuration**
   ```bash
   terraform plan
   ```

3. **Apply the Configuration**
   ```bash
   terraform apply
   ```

4. **Skip Confirmation (Optional)**
   ```bash
   terraform apply --auto-approve
   ```

---

## Additional Notes

- **IAM Role for EKS**: Create and associate an IAM role for cluster security.
- **Credentials**: Use secure methods like environment variables or a secret manager for storing keys, avoiding hardcoding sensitive data.
- **Documentation**: Refer to the official [Terraform Documentation](https://developer.hashicorp.com/terraform/docs) for further details.

---

This approach ensures a structured, reusable, and maintainable Terraform configuration for creating an EKS cluster.
