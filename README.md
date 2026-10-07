# TSTV-IoT-Cloud-Security

Python implementation and experimental evaluation of the Two-Stage Trust Verification (TSTV) framework for IoT-Cloud security.

## Overview

This repository contains the implementation and experimental materials associated with the study:

**Two-Stage Trust Verification for User and Data-Level Security in IoT-Cloud Networks**

TSTV is a sequential security workflow consisting of two verification stages:

1. **User Control Panel (UCP)** – verifies user credentials, registration status, and authorization status.
2. **Data Control Panel (DCP)** – verifies protected transaction properties, including source, destination, data-validity status, timestamp/TTL, and HMAC-based integrity and authentication.

The TSTV workflow requires successful user-level verification before the associated protected transaction proceeds to data-level verification.

## Cryptographic Components

The implementation uses established cryptographic mechanisms:

- ECC/ECDH for shared-secret establishment
- HKDF-SHA256 for session-key derivation
- PRESENT-80 for payload encryption
- HMAC-SHA256 for packet integrity and authentication
- SHA-256 for credential hashing and key derivation

These cryptographic mechanisms support the TSTV workflow and are not presented as new cryptographic primitives.

## Repository Contents

- `TSTV_IoT_Cloud_Security.ipynb` — Python implementation and experimental notebook
- `requirements.txt` — Python package dependencies
- `README.md` — repository documentation

## Experimental Evaluation

The implementation was evaluated using workloads of:

- 100 users
- 200 users
- 300 users
- 400 users
- 500 users

Ten repeated trials were performed for each workload.

The evaluation includes:

- User registration
- UCP authentication
- DCP verification
- End-to-end TSTV processing
- ECC/ECDH and HKDF session-key establishment
- Payload-size sensitivity
- Security validation using eight implemented attack scenarios
- Attack-load evaluation using 10%, 20%, and 30% attack conditions

Payload sizes from 64 to 4096 bytes were evaluated in the payload-size experiment.

## Security Validation

The implemented security scenarios include:

1. Invalid credentials
2. Unauthorized user
3. Invalid source
4. Invalid destination
5. Tampered encrypted data
6. Forged or modified HMAC
7. Invalid data-validity flag
8. Expired TTL

These experiments evaluate the verification conditions implemented in the TSTV prototype. The results should therefore be interpreted within the tested experimental conditions rather than as a universal security guarantee.

## Environment

The reported experimental environment used:

- Python 3.13.15
- NumPy 2.1.3
- Pandas 2.2.3
- cryptography 50.0.1

A fixed random seed of 42 was used for reproducibility.

## Installation

Install the required Python packages using:

```bash
pip install -r requirements.txt
