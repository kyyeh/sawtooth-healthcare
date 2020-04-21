# Sawtooth-Healthcare

# About

This is blockchain project based on Hyperledger Sawtooth. This project focuses on interaction between Insurer, 
Patient and Medical Facility. It covers data gathering flow and manages data access based on client’s role.

# Features

## Functional

- Register new users: Patient, Doctor, Clinic Desk, Lab and Insurance
- Read lists: Clinics, Doctors, Patients, Labs, Insurance, Invoice
- Read and Add records: Lab Test, Pulse, Contract, Claims
- Patient allows/revokes consent to access his data by Clinic Desk/Doctor

## Technical

- Private key to store data
- Public key to read data
- Access control: every user has a role assigned with corresponding permissions
- Docker compliance: every component of this project has separate docker image and fully isolated

## How to compile the project?

- Various network representation
1. 1 node/Dev-Mode consensus: docker-compose -f docker-compose.yaml up
2. 3 nodes/PoET consensus/single VM: docker-compose -f docker-compose-3-nodes-poet.yaml up
3. 3 nodes/PoET consensus/3 separate VMs: this is ideal and close to the reality
   a. set up 3 VMs
   b. run commands in each VM
   b1.docker-compose -f docker-compose-3-vms-0-node-poet.yaml up
   b2.docker-compose -f docker-compose-3-vms-1-node-poet.yaml up
   b3.docker-compose -f docker-compose-3-vms-2-node-poet.yaml up

# Components

- **Consent/Identity/Authorization Management** smart contract: responsible to operate with identity/permission related data
- **Data Management** smart contract: responsible to handle EHR
- **Insurance/Contract Management** smart contract: responsible to operate with insurance related data
- **Finance/Invoice Management** smart contract: responsible to operate with finances/invoices
- **REST-API service**: provides interface between client and blockchain network
- **Web client**: web page where a participant can operate as one of predefined roles such as doctor, patient etc
- **CLI client**: command line service to perform basic operations

# Architecture

![Infrastructure](https://github.com/hyperledger-labs/sawtooth-healthcare/blob/master/MedicalInsurance.png)

# Technology stack

Python/Hyperledger Sawtooth/Docker/Docker-Composer/Protobuf/Setuptools/Sanic/Shell/JMeter/Webpack

# How to setup and run infrastructure

- Go to root project’s directory
- Clone this repo
- Ensure all containers stopped: “docker-compose down --remove-orphans”
- Get recent data from the repo: “git pull”
- Start new containers: “docker-compose up”: check commands at **How to compile the project?**

# Demo
![Demo](https://github.com/kyyeh/sawtooth-healthcare/blob/master/Home.png)


