# GPT Prompt Engineering

This project provides a framework for iteratively generating and selecting optimal prompts for GPT models. 

## Overview

The key components:

- `generate_candidate_prompts()` uses GPT-4 to create multiple prompt candidates
- `test_candidate_prompts()` evaluates prompts by generating outputs and having GPT-3.5 rank them 
- Prompts are assigned ELO ratings, battled tournament-style to identify the best performers
- The top-rated prompts can be used for production systems

## Usage

To engineer prompts for a new use case:

1. Specify a `description` of the task and some `test_cases`
2. Call `generate_optimal_prompt()` with the description and test cases
3. The best prompt based on ELO rating is returned

The prompts and ratings are also optionally logged to Weights & Biases for analysis.

Several hyperparameters can be configured like models, temperatures, number of prompts etc.

## Implementation

The core functions:

- `generate_candidate_prompts()`
- `get_generation()` 
- `get_score()`
- `test_candidate_prompts()`  

Supporting functions for ELO updates, retries/backoff, and logging.

## Enhancements

Possible improvements:

- Add more models like GPT-3 Instruct, human preferences
- Enable automated fine-tuning of best prompts  
- Add more prompt filtering rules
- Deploy top prompt through API for production use
