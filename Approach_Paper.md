# Approach Paper

## PostgreSQL Replication Across Two Podman Networks

### Table of Contents  
- [Objective](#objective)  
- [Podman Network Creation](#podman-network-creation)  
- [PostgreSQL Container Setup](#postgresql-container-setup)  
- [Network Connectivity](#network-connectivity)  
- [Replication Configuration](#replication-configuration)  
- [Verification](#verification)  
- [Automation](#automation)  
- [Expected Outcome](#expected-outcome)  
- [Tools & Technologies](#tools--technologies)  
- [Conclusion](#conclusion)  

---

## Objective
The objective of this project is to set up and configure PostgreSQL replication across two separate Podman networks: `podnet1` and `podnet2`. Each network will have a Master-Slave PostgreSQL setup, and cross-network replication will be implemented between them. The goal is to ensure that:

- Queries written on `podnet1`'s Master are replicated to `podnet1`'s Slave.
- Queries written on `podnet2`'s Master are replicated to `podnet1`'s Slave.
- `podnet1` and `podnet2` are connected, enabling seamless replication.
- All container ports are uniquely assigned to prevent conflicts.

---

## Podman Network Creation
- Create `podnet1` and `podnet2` networks using Podman.

## PostgreSQL Container Setup
- Deploy PostgreSQL Master and Slave containers in `podnet1`.
- Deploy PostgreSQL Master and Slave containers in `podnet2`.
- Ensure all containers are assigned unique ports.

## Network Connectivity
- Connect PostgreSQL Master and Slave within `podnet1`.
- Connect PostgreSQL Master and Slave within `podnet2`.
- Establish connectivity between `podnet1` and `podnet2`.

## Replication Configuration
- Configure Master-Slave replication within `podnet1`.
- Configure Master-Slave replication within `podnet2`.
- Set up cross-network replication from `podnet2`'s Master to `podnet1`'s Slave.

## Verification
- Write data to `podnet1`'s Master and read from `podnet1`'s Slave.
- Write data to `podnet2`'s Master and verify replication to `podnet1`'s Slave.
- Test query consistency across both networks.

## Automation
- Podman network creation.
- PostgreSQL container setup.
- Configuration of Master-Slave replication.
- Cross-network connectivity and replication.
- Data verification.

## Expected Outcome
- Successfully configured PostgreSQL Master-Slave replication within and across Podman networks.
- A robust containerized setup with proper networking and unique port assignments.
- An automated script ensures smooth deployment and replication verification.

## Tools & Technologies
- **Podman**: For container management.
- **PostgreSQL**: Database system for Master-Slave replication.
- **Bash/Shell Scripting**: For automation of the entire setup.
- **Networking Tools**: To ensure seamless connectivity between containers.

## Conclusion
This project aims to establish a highly available and replicated PostgreSQL setup using Podman. The structured network design, along with proper replication mechanisms, ensures data consistency and reliability across multiple networks. The automation script will further streamline the deployment and testing process, making it easy to replicate the setup in different environments.

