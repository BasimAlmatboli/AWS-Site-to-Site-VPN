# AWS Site-to-Site VPN Deployment Guide

## Description

The AWS Site-to-Site VPN Deployment Guide is an open-source project providing step-by-step instructions, best practices, and resources for setting up a secure and reliable Site-to-Site VPN connection between your on-premises network and Amazon Web Services (AWS) cloud infrastructure. Source: [learn.cantrill.io](https://learn.cantrill.io/)


## Environments Used

- **AWS**

## Project Walk-through

### Some Definitions

- **AWS Site-to-Site VPN:** A logical connection between a VPC and on-premises network encrypted using IPSec, running over the public Internet.
- **HA:** Full High Availability.
- **Virtual Private Gateway (VGW):** Serves as an entry and exit point for network traffic between an organization's on-premises network or data center and the cloud infrastructure.
- **Customer Gateway (CGW):** Serves as the customer-side endpoint of a VPN connection, providing a secure link between the customer's on-premises network and the cloud infrastructure.
- **VPN Connection:** Connection between the VGW and CGW.

### Infrastructure Design

![Infrastructure Design](https://i.imgur.com/imOtfzO.png)

### Creating VPN Endpoints

#### Create a Customer Gateway

![Create Customer Gateway](https://i.imgur.com/72jOcRk.png)

#### Create a Virtual Private Gateway

![Create VGW](https://i.imgur.com/OUnRs22.png)
![Attach VGW to VPC](https://i.imgur.com/FKINbdz.png)

#### Create VPN Connection

![Create VPN Connection](https://i.imgur.com/rHgflxp.png)
![Configure VPN Connection](https://i.imgur.com/vsFL9qc.png)

#### Config on-prem pfSense

1. **Interface Assignments:**
   ![Interface Assignments](https://i.imgur.com/DymFUN0.png)
   ![LAN Configuration](https://i.imgur.com/ZJz5Elm.png)

2. **Create Phase 1 and Phase 2 of 2 IPsec Tunnels (Endpoints):**
   ![Phase 1 Configuration](https://i.imgur.com/ehbjw1u.png)
   ![Phase 2 Configuration](https://i.imgur.com/lF00UjX.png)
   ![Add Phase 2](https://i.imgur.com/Rz0Ptei.png)
   ![Configure Keep Alive](https://i.imgur.com/OtHN3x8.png)
   ![Manually Connect to IPsec](https://i.imgur.com/3Ncgzr1.png)
   ![Verify Connection](https://i.imgur.com/QAf478b.png)

### Routing and Security

#### Config Route Tables

- **Public on-prem AWS Route Propagation:**
  ![Public on-prem AWS Route Propagation](https://i.imgur.com/rGCFmak.png)
  ![Public on-prem AWS Route](https://i.imgur.com/xbDWg50.png)

- **Private on-prem AWS Route to pfSense Firewall:**
  ![Private on-prem AWS Route](https://i.imgur.com/9p9RYZV.png)

#### Edit Security Groups

1. **Default AWS Security Group:**
   ![Default AWS SG](https://i.imgur.com/W7ZTdwy.png)

2. **Default A4L Router Security Group:**
   ![Router SG](https://i.imgur.com/hlb44Zo.png)

3. **On-prem Router Security Group:**
   ![On-prem Router SG](https://i.imgur.com/8Pl6LMz.png)

## Installation

1. Clone the repository.
2. Install any necessary dependencies.

## Usage

1. Follow the steps outlined in the project walk-through.

## License

This project is licensed under the [MIT License](LICENSE).

## Contributing

Please read [CONTRIBUTING.md](CONTRIBUTING.md) for details on our code of conduct and the process for submitting pull requests.

## Troubleshooting

If you encounter any issues, refer to the [Troubleshooting Guide](TROUBLESHOOTING.md) for common solutions.

## Acknowledgments

- Thank you to [Cantrill.io](https://learn.cantrill.io/) for valuable resources.

## Contact Information

For questions or support, please contact [Basim](Basim.almatboli@gmail.com).

