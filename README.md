# Adaptive Portfolio

An experimental portfolio that detects behavioral patterns through user interaction and generates personalized audiovisual experiences.

## Overview

This project explores a question: *What if a portfolio paid attention to how you interacted with it, not just what you clicked?*

The system tracks mouse movement patterns (velocity, rhythm, hesitation, direction changes) and uses that behavioral data to classify users into interaction archetypes. Based on the classification, it generates unique audio and 3D visuals in real-time.

## How It Works

**Behavioral Fingerprinting**  
As users move through the experience, the system captures interaction signals: movement speed, dwell time, oscillation frequency, directional bias. These signals form a 6-dimensional behavioral fingerprint.

**Variational Autoencoder**  
A VAE (implemented from scratch in JavaScript) encodes the behavioral fingerprint into a latent space. The model trains on synthetic data representing four archetypes: Nervous, Contemplative, Exploratory, and Decisive.

**Generative Outputs**  
The latent vector drives procedural generation:
- 3D flowers with parameters mapped to user behavior (petal count, curl, layering)
- Reactive audio with modal harmonies, tempo, and texture shaped by interaction style
- Real-time visualizations showing the user's journey through latent space

## Files

| File | Description |
|------|-------------|
| `portfolio-orchestration.html` | Main experience controller. Manages intro sequence, video playback, 3D carousel navigation, and cross-frame communication. |
| `behavioral-vae-engine.html` | Core ML and audio system. Contains the VAE implementation, behavioral analysis, procedural music generation, and 3D flower rendering. |
| `conversational-chatbox-widget.html` | Rule-based chatbot with intent classification, conversation state tracking, and an embedded Pong game. |

## Technical Details

**Machine Learning**
- Variational Autoencoder with reparameterization trick
- KL divergence annealing to prevent posterior collapse
- Backpropagation with gradient clipping
- PCA for latent space visualization

**Audio DSP**
- Biquad filters (lowpass/highpass)
- Convolution reverb with procedural impulse response
- Ping-pong delay and LFO-modulated effects
- Modal scale selection based on behavioral profile

**Graphics**
- Three.js procedural geometry
- Real-time parameter interpolation
- Canvas-based visualizations

**Conversational System**
- Pattern-based intent classification
- Multi-turn conversation state machine
- Sentiment detection and response branching

## Status

Work in progress. Core behavioral analysis, audio generation, and VAE classification are functional. Adaptive UI personalization based on user archetype is next.

## Background

I built this to explore the intersection of behavioral psychology and generative systems. My background is in psychology and marketing. This project is how I'm teaching myself to build the technical systems underneath the ideas I want to pursue.
