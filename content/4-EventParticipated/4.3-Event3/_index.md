---
title: "Event 3 - FCAJ Mini Meeting"
date: 2026-10-24
weight: 3
chapter: false
pre: " <b> 4.3. </b> "
---

### Event Introduction

On **October 24, 2026**, I attended the **FCAJ Mini Meeting**, a technical knowledge-sharing event organized within the First Cloud AI Journey community.

The meeting covered several topics related to artificial intelligence and cloud computing, including **Vietnamese Voice AI**, **AWS Resource Access Manager (RAM)**, **AWS Security Agent**, and **Amazon Bedrock AgentCore**.

Through the presentations, I had an opportunity to learn more about how these technologies can be used in real-world systems. This report summarizes my understanding based on my notes and the presentation materials from the event.

### Event Information

- **Event Name:** FCAJ Mini Meeting.
- **Date:** October 24, 2026.
- **Role:** Attendee.
- **Main Topics:** Voice AI, AWS RAM, AWS Security Agent, and Amazon Bedrock AgentCore.

### 1. Hear, Think, Speak — Building Vietnamese Voice AI

**Kiet Tran**, an AI Engineer at Revve AI, presented **Hear, Think, Speak: Building a Vietnamese Voice-AI Contact Center on AWS**.

The session introduced how voice-based AI systems can be developed for applications such as customer service contact centers and interviews.

One point I found interesting was that a Voice AI system needs more than accurate answers. It must also detect when a user has finished speaking, process the request, and respond with sufficiently low latency to maintain a natural conversation.

#### Three Approaches to Building Voice Agents

The presentation introduced three approaches:

- **Cascade:** Divides processing into ASR → LLM → TTS. Speech is converted into text, processed by a language model, and then transformed into a spoken response.
- **Speech-to-Speech (S2S):** Uses a speech model to process audio inputs and generate audio outputs.
- **Full Duplex S2S:** Aims to support simultaneous listening and speaking, creating a more natural conversational experience.

According to the presentation, the development team continued using **Cascade in production** while experimenting with Speech-to-Speech approaches.

For their Vietnamese-language use case, Cascade offered flexibility in selecting individual components and controlling responses through an intermediate text-processing stage.

This session helped me understand that Voice AI architecture should be selected according to practical requirements, including speech quality, response latency, logging, and the ability to improve individual components.

#### Call Processing and AWS Architecture

The architecture slides introduced several components working together:

- SIP Server and Media Server.
- Noise Cancellation.
- Turn Detection.
- Speech-to-Text.
- LLM with a Flow Engine.
- Text-to-Speech.

The presentation also described Revve's deployment architecture within a single AWS Region and the customer's AWS account.

In addition, the speaker shared a proof of concept for a Vietnamese bank. The workflow involved receiving requests, verifying information, identifying user intent, and handling requests through APIs or transferring them to human agents.

This example helped me realize that a real-world Voice AI application requires both AI technologies and well-designed business workflows.

### 2. AWS Resource Access Manager — Cross-Account Resource Sharing

**Long Huynh** presented **AWS Resource Access Manager (AWS RAM)**.

The session began by discussing the challenges organizations face when managing multiple AWS accounts and sharing resources between them.

The main topics included:

- **Multi-account Challenge:** Difficulties in organizing and managing resources across multiple AWS accounts.
- **AWS RAM:** An introduction to the service and its resource-sharing capabilities.
- **Resource Share:** Defining shared resources, recipients, and permissions.
- **Sharing Workflow:** Understanding the process of sharing resources between AWS accounts.
- **Regions and Availability Zone IDs:** Important considerations regarding resource scope and deployment locations.
- **RAM in a Landing Zone:** How resource sharing can support enterprise AWS environments.

According to my notes, the speaker also mentioned that AWS RAM supports resource sharing across more than 40 AWS services.

My main takeaway was that organizations need to clearly identify **which resources are shared, which accounts can access them, and what permissions are granted**.

This session gave me an initial understanding of managing AWS infrastructure across multiple accounts rather than working with individual services in a single account.

### 3. AWS Security Agent — Securing Web Applications

**Thinh** presented **Securing Your Web Apps With AWS Security Agent**.

The session introduced an AI Agent-assisted approach to reviewing web application security.

One topic that caught my attention was **Design Security Review**.

According to the presentation, the tool can use several types of input, including:

- System design documents written in Markdown.
- Terraform infrastructure configuration files.
- Configured security requirement packs.

These inputs can support the process of evaluating a system design against defined security requirements.

This helped me understand that security reviews do not necessarily need to wait until an application is fully developed. Potential security risks can also be considered during the design stage.

The speaker also discussed costs in a section titled **The Pricing Reality**.

From this topic, I learned that organizations should consider the assessment scope and the amount of time an AI Agent spends performing tasks when estimating usage costs.

### 4. Amazon Bedrock AgentCore — Runtime and Memory

**Xuan An** presented **Amazon Bedrock AgentCore**, focusing on **Runtime** and **Memory Architecture**.

The session began with an introduction to AI Agents, Agentic AI, and Agentic Systems before exploring several AgentCore components.

#### AgentCore Runtime

The Runtime section gave me an overview of an execution environment designed for AI Agent applications.

It helped me understand that an AI Agent system needs mechanisms for executing and managing tasks rather than simply sending a request to an AI model and returning a response.

#### AgentCore Memory

The Memory section introduced how interaction information can be organized into events and related data fields.

Some concepts discussed included:

- **Memory ID:** Identifies a memory resource.
- **Actor ID:** Identifies an actor involved in an interaction.
- **Session ID:** Identifies an interaction session.
- **Payload:** Contains the recorded interaction data.
- **Timestamp:** Records when an event occurred.
- **Branch:** Represents information associated with an interaction branch.

The presentation helped me visualize how information from interaction sessions can be structured and managed to support AI Agent applications.

The meeting also briefly mentioned **Kiro Crew** and **App & Extensibility**. These are topics I would like to explore further.

### 5. Key Takeaways

After attending the FCAJ Mini Meeting, I summarized several important lessons:

- Understood the basic differences between Cascade, Speech-to-Speech, and Full Duplex Speech-to-Speech.
- Learned how Voice AI systems combine audio processing, AI models, APIs, and business workflows.
- Gained an introduction to AWS RAM and resource sharing across multiple AWS accounts.
- Recognized the value of reviewing application security during the system design stage.
- Became more aware of potential costs when using AI-assisted security assessment tools.
- Learned about Amazon Bedrock AgentCore Runtime and Memory.
- Gained an initial understanding of how interaction data and context can be organized within AI Agent systems.

### 6. Connection to My Personal Project

I am currently developing a **restaurant recommendation and itinerary planning application for Ho Chi Minh City**.

At the time of the meeting, the project was in its early development stage, with initial components such as the user interface and Backend structure taking shape.

The presentations provided useful concepts that I could consider during future development.

In particular, I realized the importance of separating system responsibilities, managing data carefully, and controlling how user requests are processed.

The security-related topics also encouraged me to pay more attention to system design and potential risks before deployment.

However, these technologies were primarily topics I explored during the meeting. **They do not represent features or AWS services that I have already implemented in my project.**

### 7. Personal Reflection

What interested me most about the FCAJ Mini Meeting was how the speakers explained the practical challenges behind real-world AI applications.

Previously, when learning about AI, I mainly focused on the models themselves. However, the Voice AI and AI Agent presentations helped me understand that many other components are necessary for a complete system.

Some topics, such as AWS RAM and AgentCore Memory, were still new to me. I would need to study additional documentation to better understand their practical applications.

Overall, the meeting broadened my knowledge of AI and AWS and gave me additional direction for future learning and project development.

### 8. Event Photos

Below are five photos from the FCAJ Mini Meeting.

#### Photo 1

![Photo 1 from FCAJ Mini Meeting](picture_event_3/1.jpg)

#### Photo 2

![Photo 2 from FCAJ Mini Meeting](picture_event_3/2.jpg)

#### Photo 3

![Photo 3 from FCAJ Mini Meeting](picture_event_3/3.jpg)

#### Photo 4

![Photo 4 from FCAJ Mini Meeting](picture_event_3/4.jpg)

#### Photo 5

![Photo 5 from FCAJ Mini Meeting](picture_event_3/5.jpg)

### Conclusion

The **FCAJ Mini Meeting on October 24, 2026**, introduced me to several topics related to Voice AI, AWS resource management, application security, and AI Agent architecture.

I was particularly interested in how practical AI systems combine different components, including data processing, AI models, APIs, Memory, and business workflows.

The presentations helped me recognize that developing AI applications involves more than selecting an AI model. It also requires careful system design, data management, and operational considerations.s