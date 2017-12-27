# Setup display with xrandr

List all connected devices
    
    # full list
    xrandr
    
    # only connected
    xrandr | grep "\scon"

Enable output for one display

    xrandr --output <name> --auto

    # set as primary monitor
    xrandr --output <name> --primary

    # set on side
    xrandr --output <name> --left-of <other_name>
    
Turn off display
   
    xrandr --output <name> --off
