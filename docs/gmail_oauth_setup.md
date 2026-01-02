# Gmail OAuth Configuration for n8n

This document describes the configuration of **Gmail authentication using OAuth 2.0** within **n8n**.  
OAuth-based authentication is used to provide secure, scoped access to Gmail through Google APIs without exposing user credentials.

---

## Overview

Gmail integration in this project is authenticated using **OAuth 2.0**, which enables token-based authorization managed by Google.  
n8n uses the issued access and refresh tokens to interact with the Gmail API in a secure and controlled manner.

---

## Authentication Method Selection

### OAuth 2.0

**Connection Type:** OAuth2  
This method is selected for Gmail authentication as it aligns with Google’s recommended approach for accessing user mailboxes.

Key characteristics:
- Token-based authentication
- Scoped permissions
- Revocable access
- No password sharing

Service Account authentication is not used, as Gmail mailbox access requires OAuth-based user consent.

---

## Credential Configuration in n8n

### Connection Settings

- **Connect using:** OAuth2
- **Allowed HTTP Request Domains:** All

The allowed domain setting permits the credential to be used with Google-managed API endpoints.  
Access control is governed by OAuth scopes defined during authorization.

---

## Authorization Flow

1. The user initiates authentication from the n8n credentials interface.
2. n8n redirects the request to Google’s OAuth authorization endpoint.
3. The user authenticates with the selected Google account.
4. Google issues access and refresh tokens upon successful consent.
5. Tokens are securely stored and managed by n8n.

At no point are account passwords shared with n8n.

---

## Credential Validation

After authorization:
- The credential status is marked as connected
- The credential becomes available for use in Gmail trigger and action nodes
- Token refresh is handled automatically by n8n

---

## Security Considerations

- OAuth tokens are stored in encrypted form
- Permissions are limited to approved Gmail scopes
- Access can be revoked from Google Account or Google Cloud Console
- Credentials are not committed to version control

---

## Usage in This Project

In this project, Gmail OAuth authentication is used to:
- Monitor incoming emails
- Access email metadata and attachments
- Trigger automated data ingestion workflows

---

## Conclusion

OAuth 2.0 provides a secure, standards-compliant authentication mechanism for integrating Gmail with n8n.  
This approach ensures controlled access, credential security, and compatibility with Google API best practices.

