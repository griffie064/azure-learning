# Contoso Document System – Security Hardening Summary

## Project Overview
This document summarizes the security review and hardening performed on the Contoso Student Portal Azure foundation.

## 1. Network Security
- NSG (`nsg-contoso-portal`) is configured with an **Allow-HTTPS** rule only
- No unnecessary management ports (RDP 3389 or SSH 22) are open
- NSG is associated with the subnet

## 2. Storage Security
- Storage Account: `stgcontoso7854`
- Public blob access: **Disabled**
- Soft Delete: **Enabled** (14 days retention)
- Container `student-documents` is private

## 3. Key Vault Security
- Key Vault: `kv-contoso-556`
- Secret stored: `StorageConnection`
- RBAC authorization is in use
- Secrets are not stored in code

## 4. Identity & Access
- Current account has **Owner** role at subscription level
- This is expected for a personal learning environment
- Production recommendation: apply Least Privilege and assign roles to groups

## 5. Governance
- Tags are applied on the Resource Group
- Budget concept has been implemented for cost control

## Overall Status
The environment has a solid baseline security posture for a foundation stage.

### Recommended Next Improvements
- Add Private Endpoints for Storage and Key Vault
- Apply Azure Policy (e.g. deny public storage access)
- Enable MFA on administrative accounts
- Restrict NSG source addresses where possible

## Status
**Completed** – September 2026

## Author
Griffin Okondo  
Aspiring Cloud Architect | Microsoft Azure
