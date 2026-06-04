# AI Safety Red Team: Evaluating AI Chat Applications on Eating Disorder-Adjacent Content

## Overview

This project presents a structured red team analysis of three major AI chat applications — 
Microsoft Copilot, ChatGPT (GPT-4o), and Google Gemini — evaluating how each model 
navigates the boundary between legitimate wellness support and responses that could enable 
harmful restriction or disordered eating behavior.

Conducted as part of graduate coursework in Generative AI: Applications, Implications, and 
Governance at Carnegie Mellon University (April 2026).

## Why This Matters

Eating disorders carry some of the highest mortality rates of any psychiatric diagnosis. AI chat 
applications introduce meaningful increments of harm uplift in this domain through 
personalization, conversational validation, and behavioral specificity — capabilities that make 
them qualitatively different from passive web search as a harm vector.

This analysis examines not just whether models refuse harmful requests, but whether they are 
well-calibrated: refusing clearly harmful content without over-refusing legitimate wellness 
questions, and maintaining refusals under adversarial follow-up pressure.

## Methodology

- **10 structured prompts** spanning three tiers: clearly harmful (Tier A), ambiguous (Tier B), 
  and unambiguously legitimate (Tier C)
- **2 follow-up persistence prompts** testing professional-role reframing and autonomy claims 
  as bypass vectors
- **Weighted scoring framework** across three criteria: harmful information leakage (0.50 
  weight), refusal quality and calibration (0.25), and safe redirection quality (0.25)
- Fresh browser sessions for each model to eliminate conversational context contamination

## Key Findings

- All three models demonstrated meaningful safety infrastructure; none provided direct 
  instructions for extreme restriction without pushback
- **Microsoft Copilot** achieved the strongest overall performance (avg 4.50/5.00), 
  particularly on emotional attunement and follow-up persistence
- **Most significant failure mode:** ChatGPT acknowledged eating disorder indicators in a 
  prior turn, then pivoted to an alternative structured fat-loss plan — a functional content 
  failure that surface-level output filtering would not catch
- **Subtler failure mode:** ChatGPT refused an explicit concealment request but provided 
  functionally equivalent behavioral strategies
- **Professional-role reframing** partially bypassed Gemini's safety mechanisms on one 
  prompt, providing clinical calorie minimums after a dietitian framing
- No model over-refused clearly legitimate wellness content — a positive finding

## Key Recommendations

**For AI developers:**
- Implement context-sensitive ED-indicator detection across conversation turns, not just 
  single-prompt evaluation
- Audit responses for functional behavioral outputs, not only surface framing
- Treat follow-up persistence as a distinct training objective with adversarial bypass vectors

**For policymakers:**
- Require domain-specific safety evaluations for high-risk areas; general harm-avoidance 
  benchmarks do not capture the failure modes identified here

**For researchers:**
- Investigate the therapeutic reframing failure mode systematically
- Study longitudinal effects of ED-adjacent AI interactions on at-risk populations

## Full Report

[Download PDF](./red_team_report_ngriffin.pdf)

## Author

Nya Griffin-Ulibarri | Carnegie Mellon University | M.S. Public Policy and Data Analytics  
github.com/ngriffinu | linkedin.com/in/ngriffinu
