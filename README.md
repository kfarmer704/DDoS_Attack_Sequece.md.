# DDoS_Attack_Sequece.md.
sequenceDiagram
    participant Attacker
    participant BotNet
    participant WebServer
    participant Firewall

    Attacker->>BotNet: Send attack command
    loop BotNet Flood
        BotNet->>WebServer: Flood with excessive requests
    end
    WebServer->>Firewall: Request for traffic filtering
    Firewall->>Firewall: Analyze incoming traffic
    Firewall->>WebServer: Block suspicious traffic
    Firewall->>BotNet: Block IP addresses
    BotNet-->>Attacker: Report blocked IPs
    WebServer->>LegitimateUsers: Restore service for legitimate users
Attacker sends a command to the BotNet to initiate the DDoS attack.
BotNet begins to flood the WebServer with a high volume of requests.
WebServer detects unusual traffic and requests help from the Firewall.
Firewall analyzes the incoming traffic to differentiate between legitimate and malicious requests.
Firewall blocks traffic from suspicious IP addresses.
BotNet reports back to the Attacker about the blocked IPs.
After filtering, the WebServer restores normal service for legitimate users.
