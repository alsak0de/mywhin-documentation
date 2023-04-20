# Introduction

Mywhin is an API-based WhatsApp client that allows users to programmatically interact with WhatsApp. This document will provide a tutorial on how to use Mywhin programmatically, assuming the user knows how to execute an HTTP request with their preferred programming language.

# Instance Management Functions

## /qrpng (GET)

This endpoint returns a QR code that must be scanned from a WhatsApp app installed on a phone in order to initiate a WhatsApp tenant.

## /status (GET)

This endpoint returns the status of your tenant. Possible values are: `active`, `sleep`, `pending enrollment`.

## /sleep (GET)

This endpoint switches the status to `sleep` state.

## /resume (GET)

This endpoint switches the tenant from `sleep` to `active` state.

## /unenroll (GET)

This endpoint wipes your instance and transitions it to `pending enrollment` state. You'll need to enroll using a new QR code to continue using the service.

# Messaging Functions

## /geturl (GET)

The response of this endpoint will be the URL defined as the webhook destination where the WhatsApp messages addressed to you will be delivered.

## /seturl (POST)

This endpoint allows you to specify a valid URL to which you want the system to deliver the WhatsApp messages to. The body of the request needs to include a valid URL in a simple string format.

## /wspout (POST)

This endpoint sends a WhatsApp message if the payload contains the right format. The payload needs to be a JSON with the following structure:

