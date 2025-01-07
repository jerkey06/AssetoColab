# AssettoColab - Assetto Corsa Server on Google Colab

Run your own Assetto Corsa server for free using Google Colab! This project allows you to host an Assetto Corsa server without the need for dedicated hardware or paid hosting services.

## Prerequisites

- A Google account
- Access to Google Drive
- An Assetto Corsa copy (for content/tracks/cars)
- (Optional) Ngrok account for custom tunneling

## Quick Start Guide

1. Open the [AssettoColab.ipynb](AssettoColab.ipynb) in Google Colab
2. Create a folder called "AC-server" in your Google Drive
3. Run the server setup cell
4. Start the server using the main server cell

## Detailed Installation Steps

### 1. Setting Up Google Colab

1. Go to [Google Colab](https://colab.research.google.com)
2. Click on `File` → `Upload Notebook`
3. Upload the `AssettoColab.ipynb` file
4. Mount your Google Drive when prompted

### 2. Server Setup

1. Run the "Server Setup" cell first. This will:
   - Create the necessary directory in your Google Drive
   - Download required server files
   - Create initial configuration files
   - Set up basic server settings

2. Wait for confirmation that all files have been downloaded and configured

### 3. Server Configuration

You can configure your server by modifying the `server_cfg.json` file in your AC-server folder. Here are the main settings:

```json
{
    "SERVER": {
        "NAME": "Your Server Name",
        "CARS": "car_model1;car_model2",
        "TRACK": "track_name",
        "MAX_CLIENTS": 24,
        "ADMIN_PASSWORD": "your_password",
        "UDP_PORT": 9600,
        "TCP_PORT": 9600,
        "HTTP_PORT": 8081
    }
}
```

#### Important Settings:

- `NAME`: Your server's display name
- `CARS`: List of allowed cars (semicolon-separated)
- `TRACK`: Track name to use
- `MAX_CLIENTS`: Maximum number of players
- `ADMIN_PASSWORD`: Password for admin access

### 4. Starting the Server

1. Run the main server cell in the notebook
2. Choose your tunneling service:
   - `argo` (default) - Easier to set up
   - `ngrok` - Requires account but potentially better performance

### 5. Connecting to Your Server

Once the server is running, you'll see a connection address in the output. Share this address with your friends to connect to your server.

Format: `hostname:port`

## Adding Custom Content

To add custom cars and tracks:

1. Navigate to your AC-server folder in Google Drive
2. Create folders:
   - `content/cars/` for custom cars
   - `content/tracks/` for custom tracks
3. Upload your content to the respective folders
4. Update your `server_cfg.json` to use the new content

## Troubleshooting

Common issues and solutions:

1. **Server Won't Start**
   - Check if all dependencies were installed correctly
   - Verify your configuration file syntax
   - Ensure ports are not blocked

2. **Connection Issues**
   - Try switching between argo and ngrok
   - Verify your firewall settings
   - Check if the server is actually running

3. **Performance Issues**
   - Reduce MAX_CLIENTS
   - Lower the CLIENT_SEND_INTERVAL_HZ
   - Consider using a different region for tunneling

## Best Practices

1. **Security**
   - Change the default admin password
   - Don't share your ngrok authentication token
   - Regularly update your server files

2. **Performance**
   - Keep track/car combinations reasonable
   - Monitor server resource usage
   - Restart the server periodically

3. **Maintenance**
   - Backup your configuration files
   - Keep track of custom content
   - Document any modifications

## Limitations

- Google Colab sessions have a time limit
- Performance may vary based on Colab's resource allocation
- Bandwidth limitations may apply
- Connection stability depends on tunneling service

## Additional Notes

- The server will stop when the Colab session ends
- You'll need to restart the server if Google Colab disconnects
- Consider setting up backup configurations
- Keep track of successful configurations for future reference

## Contributing

Feel free to contribute to this project by:
1. Reporting issues
2. Suggesting improvements
3. Submitting pull requests
4. Sharing successful configurations

## License

This project is provided as-is under the MIT License. Assetto Corsa is a product of Kunos Simulazioni, and this project is not officially affiliated with or endorsed by them.
