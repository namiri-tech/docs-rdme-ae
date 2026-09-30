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
    **Add to `~/.cursor/mcp.json`:**

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
    **Add to `~/.codeium/windsurf/mcp_config.json`:**

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
    Claude Desktop connects to remote MCP servers through the Connectors UI, not via `claude_desktop_config.json`.

    1. Open **Claude Desktop** and go to **Settings → Connectors**.
    2. Click **Add custom connector**.
    3. Enter a name (e.g. `DigiTax UAE`) and the URL:
       ```
       https://ae.docs.digitax.tech/mcp
       ```
    4. Save. To use it in a conversation, click **+** → **Add connectors** and enable **DigiTax UAE**.

  </Tab>
</Tabs>

## Testing Your MCP Setup

Once configured, you can test your MCP server connection:

1. **Open your AI editor** (Cursor, Windsurf, Claude Desktop, etc.)
2. **Start a new chat** with the AI assistant
3. **Ask about DigiTax UAE** - try questions like:
   * "How do I create a standard VAT invoice (type 380) with DigiTax UAE?"
   * "Show me an example of a Profit Margin Scheme invoice in DigiTax UAE"
   * "What fields are mandatory when creating an export invoice with delivery terms?"
   * "How do I issue a credit note referencing an original invoice in DigiTax UAE?"

The AI should now have access to your DigiTax UAE account data and documentation through the MCP server.

## Authentication

The DigiTax UAE MCP server reads live data from your account. Pass your API key as a request header:

```
X-API-Key: <your-api-key>
```

See [API Prerequisites](ref:prerequisites-of-using-the-api) for how to obtain your key and configure it in your MCP client.
