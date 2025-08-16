# Villa Website Hosting on AWS S3

This Terraform project deploys a villa website to AWS S3 with static website hosting configuration.

## 🏗️ Infrastructure Components

- **S3 Bucket**: Configured for static website hosting
- **Public Access**: Enabled for website access
- **Bucket Policy**: Allows public read access
- **Website Configuration**: Index and error document setup
- **File Uploads**: All website assets uploaded individually

## 📁 Project Structure

```
Villa-website-hosting/
├── main.tf                 # Main Terraform configuration
├── .gitignore             # Git ignore file
├── README.md              # Project documentation
├── index.html             # Main website page
├── contact.html           # Contact page
├── properties.html        # Properties listing page
├── property-details.html  # Property details page
├── assets/                # Website assets
│   ├── css/              # Stylesheets
│   ├── js/               # JavaScript files
│   ├── images/           # Image files
│   └── webfonts/         # Font files
└── vendor/               # Third-party libraries
    ├── bootstrap/        # Bootstrap framework
    └── jquery/           # jQuery library
```

## 🚀 Quick Start

### Prerequisites

- AWS CLI configured with appropriate credentials
- Terraform installed (version >= 1.0)
- Git for version control

### Deployment Steps

1. **Clone the repository**
   ```bash
   git clone <your-repo-url>
   cd Villa-website-hosting
   ```

2. **Initialize Terraform**
   ```bash
   terraform init
   ```

3. **Plan the deployment**
   ```bash
   terraform plan
   ```

4. **Apply the configuration**
   ```bash
   terraform apply
   ```

5. **Access your website**
   Visit the `website_endpoint` URL from the Terraform output.

## 🔧 Configuration Details

### S3 Bucket Configuration
- **Bucket Name**: `villa-website-hosting-{random-suffix}`
- **Region**: `us-east-1`
- **Public Access**: Enabled for website hosting
- **Website Configuration**: 
  - Index Document: `index.html`
  - Error Document: `index.html`

### File Uploads
The configuration uploads all website files individually with proper content types:
- **HTML Files**: `text/html`
- **CSS Files**: `text/css`
- **JavaScript Files**: `application/javascript`
- **Images**: `image/jpeg`, `image/png`
- **Fonts**: `font/ttf`, `font/woff2`

## 🛡️ Security Features

- **Public Access Block**: Configured to allow public read access
- **Bucket Policy**: Restricts access to read-only operations
- **Ownership Controls**: Set to bucket owner preferred

## 📊 Outputs

After successful deployment, Terraform provides:
- `bucket_name`: The name of the created S3 bucket
- `website_endpoint`: The URL where your website is accessible

## 🧹 Cleanup

To destroy the infrastructure:
```bash
terraform destroy
```

## 📝 Notes

- This configuration uses individual resource blocks for each file upload, ensuring reliability
- All Terraform state files are excluded from version control
- The bucket name includes a random suffix to ensure uniqueness
- Public access is required for static website hosting functionality

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Test the deployment
5. Submit a pull request

## 📄 License

This project is open source and available under the [MIT License](LICENSE).



