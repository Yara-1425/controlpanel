# Robot Control Pad

A simple web control pad to send commands (forward/backward/left/right/stop) to a robot via buttons or voice. Commands are stored in a MySQL database; the robot polls and reads the latest one.

## Files
- `index.html` – control UI (buttons + mic)
- `db.php` – database connection settings
- `update_command.php` – saves the command
- `get_state.php` – returns the latest command
- `setup.sql` – creates the table (run once)

## Setup
1. Run `setup.sql` in phpMyAdmin to create the `robot_state` table.
2. Edit `db.php` with your MySQL host, user, password, and database name.
3. Upload all files to the same folder on your host.
4. Open the site and use the buttons or the mic (requires HTTPS).

## Robot Integration
Poll `get_state.php` for the latest command:
```json
{ "command": "f", "updated_at": "2026-08-02 16:44:04" }
```
`f`=forward, `b`=backward, `l`=left, `r`=right, `S`=stop
