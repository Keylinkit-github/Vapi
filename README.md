# Vapi

This is the full Vapi Build, including all required API requests to build the Keylink IT AI Bot.

## API Requests

### 1. Create Transfer Tool (Deprecated?)
- **Method**: POST
- **URL**: `https://api.vapi.ai/tool`
- **Description**: This request is used to create a transfer tool with multiple destinations.
- **Body**:
  ```json
  {
    "type": "transferCall",
    "destinations": [
      {
        "type": "number",
        "number": "+16297770283",
        "message": "I am forwarding your call to Hailey. Please stay on the line."
      },
      {
        "type": "number",
        "number": "+16297770286",
        "message": "I am forwarding your call to Jeb. Please stay on the line."
      },
      {
        "type": "number",
        "number": "+16297770280",
        "message": "I am forwarding your call to Allen. Please stay on the line."
      },
      {
        "type": "number",
        "number": "+16297770281",
        "message": "I am forwarding your call to Melinda. Please stay on the line."
      },
      {
        "type": "number",
        "number": "+16297770282",
        "message": "I am forwarding your call to Craig. Please stay on the line."
      },
      {
        "type": "number",
        "number": "+16297770288",
        "message": "I am forwarding your call to Grant. Please stay on the line."
      },
      {
        "type": "number",
        "number": "+16297770285",
        "message": "I am forwarding your call to Andre. Please stay on the line."
      },
      {
        "type": "number",
        "number": "+16297770292",
        "message": "I am forwarding your call to Ethan. Please stay on the line."
      },
      {
        "type": "number",
        "number": "+16154750145",
        "message": "I am forwarding your call to a representative. Please stay on the line."
      }
    ],
    "function": {
      "name": "transferCall",
      "description": "Use this function to transfer the call. Only use it when following instructions that explicitly ask you to use the transferCall function. DO NOT call this function unless you are instructed to do so.",
      "parameters": {
        "type": "object",
        "properties": {
          "destination": {
            "type": "string",
            "enum": [
              "+16297770283",
              "16297770286",
              "+16297770280",
              "+16297770281",
              "+16297770282",
              "+16297770288",
              "+16297770285",
              "+16297770292",
              "+16154750145"
            ],
            "description": "The destination to transfer the call to."
          }
        },
        "required": ["destination"]
      }
    }
  }
  ```

### 2. Step 1) SIP Inbound
- **Method**: POST
- **URL**: `https://api.vapi.ai/tool`
- **Description**: This request is used for SIP inbound configuration.
- **Body**: Same as "Create Transfer Tool"

### 3. Step 2) SIP outbound Credential
- **Method**: POST
- **URL**: `https://api.vapi.ai/tool`
- **Description**: This request is used to configure SIP outbound credentials.
- **Body**:
  ```json
  {
    "provider": "byo-sip-trunk",
    "name": "Keylink IT 3CX Trunk",
    "gateways": [
      {
        "ip": "keylinkit.tn.3cx.us"
      }
    ]
  }
  ```

### 4. Step 3) SIP outbound Phone Number
- **Method**: POST
- **URL**: `https://api.vapi.ai/tool`
- **Description**: This request is used to configure SIP outbound phone numbers.
- **Body**: Same as "Step 2) SIP outbound Credential"

### 5. Step 4) SIP outbound Tech Prefixes
- **Method**: POST
- **URL**: `https://api.vapi.ai/tool`
- **Description**: This request is used to configure SIP outbound technical prefixes.
- **Body**: Same as "Step 2) SIP outbound Credential"
