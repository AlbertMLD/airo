# Network Management PL/SQL Package

## Overview

This PL/SQL package provides functionalities for managing network devices, interfaces, logs, and simulating traffic and alerts in an Oracle Database. The package includes procedures for setting up audit triggers to log actions on specified tables.

## Content

1. [Usage](#usage)
2. [Procedures](#procedures)
3. [Table Structure](#table-structure)
4. [Security Considerations](#security-considerations)
5. [Testing](#testing)
6. [Dependencies](#dependencies)
7. [Contributing](#contributing)
8. [License](#license)

## Usage

1. Execute the SQL script to create the `network_management` package and package body in your Oracle Database.

    ```sql
    -- Execute the script containing the package and package body
    @your_script.sql
    ```

2. Use the provided procedures to manage network devices, interfaces, logs, and simulate traffic and alerts.

## Procedures

- **`create_and_insert_network_devices`**: Creates a table for network devices and inserts sample data.
- **`add_device`**: Inserts a new device into the network_devices table.
- **`create_and_insert_network_interfaces`**: Creates a table for network interfaces and inserts sample data.
- **`delete_device`**: Deletes a device from the network_devices table based on the provided device_id.
- **`setup_audit_triggers`**: Sets up audit triggers for specified tables to log insert, update, and delete actions.
- **`simulate_traffic_and_alerts`**: Simulates network traffic and generates alerts based on traffic conditions.
- **`create_and_insert_network_logs`**: Creates a table for network logs and inserts sample data.

## Table Structure

The package creates the following tables:

- `network_devices`: device_id, device_name, device_ip_address, device_type, location, manufacturer, firmware_version, status, last_seen - (Stores information about network devices).
- `network_interfaces`: interface_id, device_id, interface_name, interface_type, speed_mbps, mac_address - (Stores information about network interfaces).
- `audit_logs`: audit_id, administrator_id, timestamp, action_type, table_affected, record_id, details - (Logs actions (insert, update, delete) on specified tables).
- `trafic_interfete`: interfata_id, nume_interfata, trafic_in_10G, trafic_out_10G, trafic_in_40G, trafic_out_40G, trafic_in_100G, trafic_out_100G, timestamp - (Stores simulated network traffic data).
- `alerte_trafic`: alerta_id, interfata_id, nume_interfata, tip_alerta, timestamp - (Stores alerts generated based on simulated traffic conditions).
- `network_logs`: log_id, device_id , interface_id, timestamp, log_message, log_level, source_ip - (Stores network log data).

## Security Considerations

- Ensure that input parameters are properly validated to prevent SQL injection.
- Grant appropriate permissions to the user executing the procedures.

## Testing

Thoroughly test each procedure in a controlled environment to ensure correct functionality. Pay special attention to error handling and edge cases.

## Dependencies

No external dependencies are required. Ensure the Oracle Database environment is properly configured.

## Contributing

If you find issues or have suggestions for improvement, feel free to contribute by opening an issue or submitting a pull request.

## License

This code is licensed under the [AlbertMLD License](LICENSE).
