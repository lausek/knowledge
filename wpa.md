# Connect to a new network

## Interactively 

Use this to get into interactive session
    
    sudo wpa_cli

Scan environment with and wait for RESULT 
    
    scan

Retrieve available networks with

    scan_result

Create a new network
    
    add_network

`<id>` is a unique intern number which identifies the network. Set the networks information with `set_network` 

    set_network <id> ssis "SSID"
    set_network <id>  psk "psk"

    # for networks without key
    set_network <id> 0 key_mgmt NONE

Activate network
    
    enable_network <id>

Save
    
    save_config

## Oneliner

Use `wpa_passphrase` to directly connect

    wpa_passphrase SSID psk > /etc/wpa_supplicant/<network>.conf
