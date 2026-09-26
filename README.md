# KLH-CSE-2026-2030-JAVA-Online-Store-Cart-Order-Pipeline
This project implements a clean and scalable Cart &amp; Order Pipeline for an online store. It handles adding/removing items, calculating totals (including tax &amp; discounts), creating orders, updating inventory, and managing order status transitions through a well-structured pipeline.
# 🛒 Online Store Cart & Order Pipeline

A console-based Java application that simulates a complete e-commerce flow — from browsing products to placing an order — built as a single integrated program from 12 modular components (product catalog, cart, inventory, checkout, payment, order confirmation, and more).

---

## 📌 Overview

This project began as 12 separate mini-modules, each responsible for one piece of an online shopping experience (catalog, cart, inventory, user session, checkout, order, payment, confirmation, storage, UI, validation, utilities). They have been merged into a single cohesive Java program (OnlineStore.java) that runs a real, menu-driven shopping pipeline in the terminal.

Customer details — name and mobile number — are collected live via Scanner input at checkout instead of being hardcoded, making the flow behave like a genuine order-taking system.

---

## ✨ Features

- 📋 Product Catalog — browse all products or search by keyword
- 🛍 Shopping Cart — add, remove, and update item quantities
- 📦 Live Inventory Tracking — stock is checked before adding to cart and decremented after a successful payment
- 👤 Guest Session Handling — lightweight session tracking (extensible to full login/registration)
- 📝 Checkout with Live Input — name, mobile number, address, city, and pincode collected via Scanner, with field validation (required fields, 10-digit mobile, 6-digit pincode)
- 💰 Automatic Pricing — 5% tax calculation + free shipping over ₹1000 (flat ₹50 below that)
- 💳 Simulated Payment Gateway — choose Card / COD / UPI, with a randomized success/failure outcome
- ✅ Order Confirmation — printed receipt with a masked mobile number and a simulated email notification
- 💾 In-Memory Order & Product Storage — plus a simulated "file write" for persisted order records
- 🔁 Retry-Friendly — failed payments keep the cart intact so checkout can be retried

---

## 🗂 Project Structure

The entire pipeline lives in one file, OnlineStore.java, composed of the following classes:

| Class | Responsibility |
|---|---|
| Product | Represents a single product (id, name, price, description, image, stock) |
| ProductCatalog | Loads, lists, searches, and looks up products |
| Inventory | Checks and decreases stock, synced with ProductCatalog |
| CartItem / ShoppingCart | Manages cart items: add, remove, update, total, display |
| User / UserSession | Basic user model and guest/login session tracking |
| Validator | Shared validation logic (quantity, required fields, cart, payment result) |
| Checkout | Collects and validates shipping details via Scanner |
| OrderItem / Order / OrderModule | Builds an order from the cart and stores it |
| Payment | Simulates payment processing across Card / COD / UPI |
| OrderConfirmation | Prints the final confirmation receipt |
| DataStorage | In-memory storage + simulated file persistence for orders/products |
| Utility | Price formatting, unique ID generation, timestamps, tax & shipping math |
| OnlineStore | main() — the interactive menu that ties every module together |

---

