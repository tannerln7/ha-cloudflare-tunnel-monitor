  
  

## Enable Cloudflared Tunnel Metrics
Official Cloudflare documentation (generic guide to edit the tunnel run command on Linux, macOS, and Windows). 

At step 2 of this guide, add the configuration flags described below to your tunnel run command.

https://developers.cloudflare.com/cloudflare-one/networks/connectors/cloudflare-tunnel/configure-tunnels/cloudflared-parameters/#update-tunnel-run-parameters

## Add the Metrics Flag
In the existing run command, add `--metrics <address>:<port>` after `tunnel` and before `run`

**Format:**

```
cloudflared tunnel --metrics <address>:<port> run <tunnel-name> --token YOUR_TUNNEL_TOKEN
```

  

**Example (localhost only):**

  

```
cloudflared tunnel --metrics 127.0.0.1:20241 run my-tunnel --token YOUR_TUNNEL_TOKEN
```

  

**If you want the metrics endpoint accessible from your LAN:**

  

```
cloudflared tunnel --metrics 0.0.0.0:20241 my-tunnel --token YOUR_TUNNEL_TOKEN
```

  

## Restart Cloudflared

  

After updating the run command, restart the cloudflared service as described in the Cloudflare guide linked above.

  

Use the ip address of your cloudflared tunnel device and the port you added to the tunnel run command when configuring the metrics URL in home assistant.