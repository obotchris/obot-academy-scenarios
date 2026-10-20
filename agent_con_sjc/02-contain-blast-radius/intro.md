# Lab B: Contain the Blast Radius

**Goal:** rebuild the *same* integration so the attack from Lab A can't happen — using two controls that live outside the model: **least privilege at the tool level** (a Managed vMCP) and **data filtering at the gateway**.

In this lab you'll:

1. Break the trifecta by building a **Managed** vMCP (`support-safe`) that exposes only the tools a support agent actually needs
2. Re-run the Lab A attack against the safe surface and watch it become structurally impossible
3. Add a source catalog with a clean PII data source
4. Create a gateway **redaction** filter and verify it
5. Switch to **blocking**, then learn — the hard way — why you must test filters

This lab assumes you've completed **Lab A**.

> **What changed in v0.26:** the old "composite server" is gone. Least privilege is now expressed by creating a **Managed** vMCP and disabling the tools you don't want — the same idea, the current mechanism.
