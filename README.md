{
  "log": {
    "loglevel": "warning"
  },
  "inbounds": [
    {
      "port": 1080,
      "listen": "127.0.0.1",
      "protocol": "socks",
      "settings": {
        "auth": "noauth",
        "udp": true,
        "ip": "127.0.0.1"
      }
    }
  ],
  "outbounds": [
    {
      "protocol": "vmess",
      "settings": {
        "vnext": [
          {
            "address": "your-vps-address",
            "port": 443,
            "users": [
              {
                "id": "your-uuid",
                "alterId": 0,
                "security": "auto"
              }
            ]
          }
        ]
      },
      "streamSettings": {
        "network": "ws",
        "security": "tls",
        "tlsSettings": {
          "allowInsecure": true,
          "serverName": "cdn-tanzania.marmot-cloud.com"
        },
        "wsSettings": {
          "path": "/vmess"
        }
      }
    },
    {
      "protocol": "trojan",
      "settings": {
        "servers": [
          {
            "address": "your-vps-address",
            "port": 443,
            "password": "your-password",
            "level": 8
          }
        ]
      },
      "streamSettings": {
        "network": "ws",
        "security": "tls",
        "tlsSettings": {
          "allowInsecure": true,
          "serverName": "cdn-tanzania.marmot-cloud.com"
        },
        "wsSettings": {
          "path": "/trojan-ws"
        }
      }
    }
  ]
}
