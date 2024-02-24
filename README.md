# MAC Address Changer

This Python script provides a simple interface for changing the MAC (Media Access Control) address of a network interface on a Unix-based system. This can be useful for enhancing privacy and security or overcoming network restrictions.

## Usage

### Prerequisites
- Ensure that Python is installed on your system.
- The script requires elevated privileges, so it should be run with `sudo` or as a superuser.

### Command-line Options
- `-i, --interface`: Specify the network interface for which you want to change the MAC address.
- `-m, --mac`: Set the new MAC address that you want to assign.

### Example
```bash
sudo python mac_changer.py -i eth0 -m 00:11:22:33:44:55
```

## Code Structure

### `get_arguments()`
- Parses command-line arguments using `optparse` to retrieve the specified network interface and new MAC address.
- Displays an error if essential arguments are not provided.

### `change_mac(interface, new_mac)`
- Utilizes subprocess calls to bring down the specified interface, assign a new MAC address, and bring the interface back up.
- Prints a success message upon successful MAC address change.

### `get_current_mac(interface)`
- Retrieves the current MAC address of the specified interface by parsing the output of the `ifconfig` command.
- Returns the current MAC address or displays an error if it cannot be determined.

### Main Execution
- Retrieves and displays the current MAC address of the specified interface.
- Calls `change_mac()` to change the MAC address to the user-provided value.
- Retrieves the current MAC address again and confirms whether the change was successful.

## Important Note
- This script is designed for Unix-based systems and requires elevated privileges to execute.
- Understand the potential risks and legal implications before attempting to change MAC addresses.

Feel free to contribute, report issues, or provide feedback to enhance the functionality of this MAC address changer script. Happy coding!
