# Backend: Services Repository

Parent repository containing the core business microservices for the Pet Clinic system, linked as Git submodules.

## Student Information
- **Student Name:** Isuri Gamage
- **Student Number:** 241722008
- **Slack Handle:** 
- **GCP Project ID:** 

## Project Description
This is the parent repository for the business logic microservices of the Pet Clinic system. It links three independent repositories as Git submodules: the Owner Service, the Pet Service, and the Appointment Service. Together, these services implement the core functionality of the Pet Clinic application, demonstrating the use of both relational (MySQL) and non-relational (MongoDB) databases as required by the module.

## Technology Stack
- **Language:** Java 25
- **Framework:** Spring Boot, Spring Cloud, Spring Data
- **Databases:** MySQL (owner-service, appointment-service), MongoDB (pet-service)
- **Build Tool:** Maven
- **Cloud Platform:** Google Cloud Platform (GCP) — deployed as IaaS on Compute Engine, with auto-scaling
- **Process Management:** PM2
- **Repository Structure:** Polyrepo with Git Submodules

## Submodules
| Component | Description | Database | Repository |
|-----------|-------------|----------|------------|
| `owner-service` | Manages pet owner records | MySQL | [owner-service](https://github.com/Isuri15/owner-service) |
| `pet-service` | Manages pet records and image uploads | MongoDB | [pet-service](https://github.com/Isuri15/pet-service) |
| `appointment-service` | Manages veterinary appointment bookings | MySQL | [appointment-service](https://github.com/Isuri15/appointment-service) |

## Setup / Getting Started

### Cloning with Submodules
```bash
git clone --recurse-submodules https://github.com/Isuri15/backend-services.git
```

If already cloned without submodules:
```bash
git submodule update --init --recursive
```

### Prerequisites
Before starting any of these services, ensure the platform components are running:
1. `eureka-server` (port 8761)
2. `config-server` (port 8888)

### Run Order
1. `owner-service` (port 8081)
2. `pet-service` (port 8082)
3. `appointment-service` (port 8083)
4. `api-gateway` (port 8080) — after all business services are running

Refer to each submodule's own README.md for detailed setup instructions.

## Cloud Deployment
All three microservices are deployed on Google Cloud Platform using an IaaS model (Compute Engine VM Instance Groups) with auto-scaling enabled, ensuring the services can handle variable load without running as single fixed instances.

## Related Repositories
- [backend-microservices-platform](https://github.com/Isuri15/backend-microservices-platform) — platform components (Eureka, Config Server, API Gateway)
- [frontend-web-app](https://github.com/Isuri15/frontend-web-app) — frontend application
