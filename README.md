Meta-LoRA: Sublinear Memory Scaling for Multi-Task LoRA Fine-Tuning

This project implements Meta-LoRA, a proof-of-concept method that reduces the memory cost of LoRA adapters when scaling to many tasks. Instead of storing a full LoRA adapter per task (linear growth), Meta-LoRA shares a common subspace and only stores task-specific coefficients. Residuals are stored once globally, which shifts scaling from linear to sublinear.

Motivation

LoRA (Low-Rank Adaptation) is widely used for parameter-efficient fine-tuning of large language models.

Problem: For T tasks, LoRA requires storing T independent adapters → linear storage growth.

Meta-LoRA solves this by:

Learning a shared low-rank basis across tasks

Storing compact per-task coefficients

Storing residuals once globally

This provides memory savings after a small number of tasks.
