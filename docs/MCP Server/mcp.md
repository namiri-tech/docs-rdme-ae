---
title: MCP
excerpt: Learn how to use DigiTax UAE's MCP server
deprecated: false
hidden: false
metadata:
  robots: index
---
MCP stands for Model Context Protocol. Read more about it in the [official documentation](https://modelcontextprotocol.io/).

The DigiTax UAE Model Context Protocol (MCP) server enables AI-powered code editors like Cursor and Windsurf, plus general-purpose tools like Claude Desktop, to interact directly with your DigiTax UAE API and documentation.

## What is MCP?

Model Context Protocol (MCP) is an open standard that allows AI applications to securely access external data sources and tools. The DigiTax UAE MCP server provides AI agents with:

* **Direct API access** to DigiTax UAE functionality
* **Documentation search** capabilities
* **Real-time data** from your DigiTax UAE account
* **Code generation** assistance for DigiTax UAE integrations

## DigiTax UAE MCP Server Setup

DigiTax UAE hosts a remote MCP server at `https://ae.docs.digitax.tech/mcp`. Configure your AI development tools to connect to this server. If your APIs require authentication, you can pass in headers via query parameters or however headers are configured in your MCP client.

<Tabs>
  <Tab title="Cursor">
    **Add to&#x20;**`~/.cursor/mcp.json`**:**

    ```json
    {
      "mcpServers": {
        "ae-dgtax": {
          "url": "https://ae.docs.digitax.tech/mcp"
        }
      }
    }
    ```
  </Tab>

  <Tab title="Windsurf">
    **Add to&#x20;**`~/.codeium/windsurf/mcp_config.json`**:**

    ```json
    {
      "mcpServers": {
        "ae-dgtax": {
          "url": "https://ae.docs.digitax.tech/mcp"
        }
      }
    }
    ```
  </Tab>

  <Tab title="Claude Desktop">
    **Add to&#x20;**`claude_desktop_config.json`**:**

    ```json
    {
      "mcpServers": {
        "ae-dgtax": {
          "url": "https://ae.docs.digitax.tech/mcp"
        }
      }
    }
    ```
  </Tab>
</Tabs>

## Testing Your MCP Setup

Once configured, you can test your MCP server connection:

1. **Open your AI editor** (Cursor, Windsurf, Claude Desktop, etc.)
2. **Start a new chat** with the AI assistant
3. **Ask about DigiTax UAE** - try questions like:
   * "How do I create a standard VAT invoice (type 380) with DigiTax UAE?"
   * "Show me an example of a Profit Margin Scheme invoice using tax category N"
   * "What fields are mandatory when creating an export invoice with delivery terms?"
   * "How do I issue a credit note referencing an original invoice in DigiTax UAE?"

The AI should now have access to your DigiTax UAE account data and documentation through the MCP server.

<br />

<Callout icon="📘" theme="info">
  ### Found something wrong in an AI answer?

  These tools read our live spec and documentation, but AI assistants can
  still misread, over-generalise, or give an answer that's out of date.
  If an answer looks wrong — a field that doesn't exist, a validation rule
  that doesn't match what the API actually does, or a contradiction between
  two pages — please tell us.

  <Anchor target="_blank" href="mailto:support@namiri.tech">Email us</Anchor> or use the **DigiTax Support** at the<br />top-right of any page on the dashboard.

  It helps us if you include:

  - the question you asked
  - the answer you got
  - the endpoint or page it relates to, if you know it
</Callout>
