
## NYC Taxi Data Engineering Pipeline 🚖  
*A beginner-friendly batch ETL project for modern data engineers*

> 📍 This project is adapted and extended from the tutorial: [Data Engineering Project for Beginners – Batch Edition](https://www.startdataengineering.com/post/data-engineering-project-for-beginners-batch-edition/)  
> 🛠️ Built and maintained by **Yanxiang Du**

---

## 🚀 Project Overview

This data pipeline demonstrates how to extract, transform, and load (ETL) real-world data using industry-standard open-source tools.  
It uses Apache Airflow to orchestrate a batch pipeline for processing NYC taxi trip data and stores the results in PostgreSQL and DuckDB. It also integrates Spark for computation and MinIO as an object storage system.

You can run the entire project either **locally** or in **GitHub Codespaces** using Docker Compose.

---

## 🧰 Tech Stack

| Tool            | Purpose                              |
|-----------------|---------------------------------------|
| Apache Airflow  | Workflow orchestration (DAGs)         |
| Apache Spark    | Data processing & transformation      |
| DuckDB          | Analytical database / data warehouse  |
| PostgreSQL      | Metadata and staging storage          |
| MinIO           | S3-compatible object storage          |
| Docker          | Containerized execution               |
| GitHub Actions  | CI/CD and automated testing           |
| Quarto + Plotly | Dashboard visualization               |

---

## 🏗️ Architecture

![Architecture](assets/images/arch.png)

This pipeline includes:

- Batch extraction and transformation of taxi trip data
- Spark job to process and classify user activity
- Visualization with Quarto dashboard
- CI/CD integration with `make` commands and GitHub Actions

Final rendered dashboard is located at:  
📄 `./dags/scripts/dashboard/dashboard.html`

---

## ⚙️ Run the Project

### ▶️ Run on GitHub Codespaces

1. Fork this repository  
2. Click `Code` → `Codespaces` → `Create codespace on main`  
3. After container is ready, run the following:

```bash
make up
sleep 30
````

4. Access Airflow UI via the `Ports` tab → port `8080`

   * Username: `airflow`
   * Password: `airflow`

---

### 🖥️ Run Locally

#### Requirements

* Git
* Docker with ≥ 4GB memory
* Docker Compose v1.27.0+
* Python (optional, for dashboard script)

#### Steps

```bash
git clone https://github.com/YOUR_USERNAME/data-engineering-pipeline.git
cd data-engineering-pipeline
make up
sleep 30
make ci  # run quality checks and tests
```

Visit Airflow UI at [http://localhost:8080](http://localhost:8080)
Login: `airflow` / `airflow`

---

## 📝 DAG Example

Example DAG: `user_analytics_dag`
This pipeline extracts and transforms data, loads to warehouse, and generates insights via dashboard.

![DAG](assets/images/dag.png)

---

## 📊 Output Dashboard

After pipeline completes, you can open the result at:

```
./dags/scripts/dashboard/dashboard.html
```

It includes user engagement summaries and classification result.

---

## 🧠 Lessons & Highlights

* Designed and orchestrated an end-to-end batch ETL pipeline using Airflow DAGs
* Applied Spark for scalable transformation
* Integrated Quarto for automated HTML dashboard rendering
* Used MinIO to emulate cloud storage locally
* Adopted CI/CD principles using `make`, GitHub Actions, and containerization

---

## 📌 Credits

This project is based on the excellent tutorial by [Start Data Engineering](https://www.startdataengineering.com/).
Originally created by [josephmachado](https://github.com/josephmachado/beginner_de_project) and adapted by **Yanxiang Du** for personal learning and portfolio.

```


