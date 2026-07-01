# MS-thesis-data-pipeline
Intelligent Multi-Modal Data Pipeline for Large-Scale E-Commerce Data
# Intelligent Multi-Modal Data Pipeline for Large-Scale E-Commerce Data

**Built a smart data pipeline that processes 1.4M+ e-commerce product records (text + images) and automatically routes each record through the most efficient processing path  cutting processing time by up to 231x while maintaining accuracy.**

---

## The Problem

E-commerce platforms manage millions of products, each containing a mix of text descriptions, categories, and images. Most data pipelines treat every record the same way  running every single one through expensive deep-learning image models, even when there's no image to process. This wastes massive amounts of compute time and money, and slows everything down as the dataset grows.

## What I Built

An **Intelligent Modality Router** — a pipeline that thinks before it processes:

- Scans each incoming product record automatically
- Detects whether it has an image or is text-only
- Routes image-based products to a dual AI vision system (**ResNet50 + VGG16 ensemble**) for deep visual feature extraction
- Routes text-only products to a faster hybrid text engine (**TF-IDF + 1D-CNN**) skipping the expensive vision models entirely
- Automatically falls back to text-only processing if an image is missing or broken, so the pipeline never stalls

## Key Results

| Metric | Result |
|---|---|
| Dataset size | 1.4 million real e-commerce records (Amazon product data) |
| Throughput | ~18 records/second, stable even as load scaled from 100 to 5,000 records |
| Speed gain | Up to **231x faster** for text-only records vs. running every record through full AI models |
| Reliability | Statistically validated (low variance, 95% confidence) results are consistent, not a one-off lucky run |
| Memory efficiency | Processed 1.4M records on a standard 16GB RAM machine using streaming/chunked data loading |

## Tech Stack

`Python` · `TensorFlow / Keras` · `ResNet50` · `VGG16` · `scikit-learn (TF-IDF)` · `Pandas` · `NumPy` · `OpenCV`

## Why This Matters for Businesses

This architecture is directly applicable to:

- **Recommendation engines**  faster, cheaper product matching at scale
- **Content moderation**  auto-flagging text and images without processing everything through heavy models
- **Digital asset management**  organizing large mixed-media catalogs efficiently
- **Any system handling mixed data types (text + images)** where speed and infrastructure cost matter

---

*This project was developed as part of an MS research thesis in Data Science and demonstrates applied skills in large-scale data engineering, multi-modal machine learning, and performance optimization directly transferable to production data pipelines and AI systems for businesses.*
