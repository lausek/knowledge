# Connect to a new network

**Note:** Depending on the networks IP assignment configuration, this could require a change of the network interface in `/etc/network/interfaces`. 

## Interactively 

Use this to get into interactive session
    
    sudo wpa_cli

Execute environment scan and wait for `RESULT` message 
    
    scan

Retrieve available networks with

    scan_result

List all configured networks where the first column is the networks `<id>`

    list_network

Create a new network
    
    add_network

`<id>` is a unique intern number which identifies the network. Set the networks information with `set_network` 

    set_network <id> ssid "SSID"
    set_network <id>  psk "psk"

    # for networks without key
    set_network <id> 0 key_mgmt NONE

Activate network
    
    enable_network <id>

Save
    
    save_config

## Oneliner

Use `wpa_passphrase` to directly connect if ssid and psk are known

    wpa_passphrase <ssid> <psk> > /etc/wpa_supplicant/<network>.conf
