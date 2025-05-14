# 📘 HDR UK Gateway - Feature Configurations

Welcome to the HDR UK **feature configuration repository**!

This repository is used to manage which features are **enabled or disabled** for both:

- [Gateway API](https://github.com/HDRUK/gateway-api) – backend built with Laravel
- [Gateway Web](https://github.com/HDRUK/gateway-web) – frontend built with Next.js

## 📁 Folder Structure

The repository contains three environment folders:

- `dev/`
- `preprod/`
- `prod/`

Each folder includes a JSON configuration file for that specific environment. These configurations allow us to enable or disable features **without requiring deployments or rebuilding** the applications.

## ⚙️ Feature Flag Frameworks

- **Gateway API** uses [Laravel Pennant](https://laravel.com/docs/12.x/pennant) to manage feature flags.
- **Gateway Web** uses [Next.js Feature Flags](https://vercel.com/docs/feature-flags/feature-flags-pattern) to manage flags within the frontend.

## 🧾 Example Configuration

Below is an example of a feature configuration file:

```json
 {
    "createDatasets": {
      "enabled": true
    },
    "upload": {
      "enabled": false
    },
    "gmi": {
      "enabled": true,
      "features": {
        "auth": {
          "enabled": true
        },
        "no-auth": {
          "enabled": false
        },
        "privateApps": {
          "enabled": false
        }
      }
    }
  }
