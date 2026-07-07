---
layout: ../layouts/ContentLayout.astro
title: Getting Started with NATS Toolbox
description: Install NATS Toolbox, connect to a NATS server, and start exploring JetStream, Core NATS, services, and Key/Value data.
---

# Getting Started with NATS Toolbox

NATS Toolbox brings JetStream, Core NATS, services, and Key/Value data into your
JetBrains IDE. Follow these steps to connect your first server and explore its
resources.

## 1. Install NATS Toolbox

1. Open **Settings | Plugins** in your JetBrains IDE.
2. Select the **Marketplace** tab.
3. Search for **NATS Toolbox**, or open the
   [JetBrains Marketplace page](https://plugins.jetbrains.com/plugin/32647-nats-toolbox).
4. Click **Install** and restart the IDE if prompted.

## 2. Create a connection

1. Open **View | Tool Windows | NATS Toolbox**.
2. Click **Manage...**.
3. Create a connection profile and enter your NATS server URL, for example
   `nats://localhost:4222`.
4. Configure authentication or TLS when required by your server.
5. Save the profile, select it, and click **Connect**.

NATS Toolbox supports tokens, username and password, NKeys, credentials files,
and TLS. Secrets are stored using the IDE Password Safe.

When JetStream is available, streams and Key/Value buckets are loaded
automatically. Core NATS features remain available when the server does not have
JetStream enabled.

## 3. Explore a stream

Expand **Streams** and open a stream to inspect its configuration and consumers.
The stream editor also provides two message workflows:

- **Messages** searches stored messages by subject, sequence, sequence range, or
  payload content. Results can be sorted in either direction and viewed page by
  page.
- **Live** subscribes to new stream messages. Multiple subject-filtered
  subscriptions can run at the same time.

## 4. Decode message payloads

Select a message and use **Configure...** above its details to choose a payload
decoder.

Available decoders include:

- plain text;
- hexadecimal;
- Protocol Buffers from a `.proto` file or descriptor set.

Decoder rules can be assigned to subject patterns when one stream contains
different message types. Advanced decoder settings can trim leading or trailing
bytes before decoding, which is useful for schema identifiers or custom
envelopes.

## 5. Use Core NATS

Open **Core NATS | Console** from the tool window.

- Use **Listen** to subscribe to subjects and wildcards. You can keep multiple
  subscriptions active and inspect messages from each session.
- Use **Request** to send request/reply calls with an explicit timeout.

Core NATS does not require JetStream.

## 6. Discover NATS services

Open **Core NATS | Services** to discover services that implement the standard
NATS service protocol. You can inspect instances, endpoints, request counts,
errors, and latency, then call an endpoint and inspect its response.

## 7. Browse Key/Value data

Expand **Key/Value**, open a bucket, and select a key to inspect its current
value and metadata. Payload decoder rules can also be used for Key/Value values.

> NATS Toolbox provides read-only access. It does not modify streams, consumers,
> messages, or Key/Value entries.
