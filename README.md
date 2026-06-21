Microsoft Fabric Sizing & Cost Calculator

A lightweight, interactive web tool designed to help data architects, engineers, and decision-makers estimate the monthly running costs of migrating large-scale data workloads to Microsoft Fabric.

Unlike standard pricing calculators, this tool evaluates the physics of your workload—taking into account concurrent jobs, refresh intervals, and ETL strategies (Incremental vs. Full Load) to warn you if your chosen capacity (SKU) will bottleneck or throttle.

Features

Real-time Cost Estimation: Instantly calculates estimated monthly costs in AUD as you adjust workload parameters.

Storage vs. Compute Breakdown: Clearly separates OneLake storage costs from Fabric Compute (CU) costs, highlighting the often-forgotten data footprint cost.

Architecture Validation: Dynamically displays warnings if your workload parameters (e.g., refreshing 100TB every 15 minutes with a Full Load) will melt your selected compute capacity.

Pricing Models: Toggle between Pay-As-You-Go and 1-Year Reserved pricing to see potential savings.

Zero Dependencies: Runs entirely in the browser using a single HTML file styled with Tailwind CSS via CDN.

How to Run

Download or clone the index.html file.

Double-click the file to open it in any modern web browser (Chrome, Edge, Firefox, Safari).

No build steps, Node.js, or local servers are required.

Understanding the Inputs

Workload Parameters

Total Data Volume (At Rest): The total physical size of your data stored in OneLake (in Terabytes). This directly drives the storage cost.

15-Minute Refresh Volume: The volume of data (in TB) targeted for near-real-time updates every 15 minutes.

Daily Refresh Volume: The volume of data (in TB) processed during standard daily batch windows.

Peak Concurrent Jobs: The maximum number of pipelines, notebooks, or jobs running simultaneously. High concurrency requires specific architectural patterns (like Spark Session Sharing) to avoid queue limits.

Configuration

15-Min Refresh Strategy: * Incremental (CDC / Delta Merge): Highly efficient. Only processes changed rows.

Full Load (Truncate & Load): Highly resource-intensive. Physically rewrites the entire target table.

Compute SKU: Select your target Fabric Capacity (F256, F512, F1024, or F2048).

Pricing Model: Choose between standard Pay-As-You-Go rates or discounted 1-Year Reserved instances.

Pricing Assumptions & Baseline (AUD)

Prices are hardcoded estimates for the Australia East region and are meant for directional sizing. Always consult the official Microsoft Azure Pricing Calculator for formal quotes.

OneLake Storage: ~$0.039 AUD per GB / month.

Compute (Pay-As-You-Go):

F256: ~$57,000 / month

F512: ~$114,000 / month

F1024: ~$228,000 / month

F2048: ~$456,000 / month

Compute (1-Year Reserved): Includes an approximate 40% discount over PAYG rates.

Built With

HTML5 / Vanilla JavaScript

Tailwind CSS (via CDN)
