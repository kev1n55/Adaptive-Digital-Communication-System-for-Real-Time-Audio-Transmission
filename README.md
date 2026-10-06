# Adaptive Digital Communication System for Real-Time Audio Transmission

A MATLAB/Simulink implementation of an adaptive digital communication system designed for reliable transmission of real audio signals under varying AWGN channel conditions.

## Overview

A fixed digital communication configuration may not provide the best performance under different channel conditions or for different types of audio signals.

This project develops an adaptive communication system that evaluates different combinations of:

- Source coding
- Line coding
- Digital modulation

and automatically selects a suitable configuration based on measured communication performance.

The system is designed to work with real speech or music signals and evaluates the selected configuration using multiple performance parameters rather than relying on a single metric.

## System Architecture

```text
Real Audio Signal
       ↓
    Sampling
       ↓
 ┌─────────────────────┐
 │   Source Coding     │
 │ PCM / DPCM / DM     │
 └──────────┬──────────┘
            ↓
       Bit Stream
            ↓
 ┌─────────────────────┐
 │    Line Coding      │
 │ NRZ-L / Manchester  │
 │ / AMI               │
 └──────────┬──────────┘
            ↓
 ┌─────────────────────┐
 │ Digital Modulation  │
 │ QPSK / 16-QAM /     │
 │ 64-QAM              │
 └──────────┬──────────┘
            ↓
       AWGN Channel
            ↓
       Demodulation
            ↓
      Line Decoding
            ↓
      Source Decoding
            ↓
  Reconstructed Audio
            ↓
 Performance Evaluation
            ↓
   Adaptive Selection
