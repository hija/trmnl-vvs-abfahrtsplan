# VVS Departures Plugin for TRMNL

A TRMNL plugin that displays real-time departure information for public transportation stations in the VVS (Verkehrs- und Tarifverbund Stuttgart) network.

## Screenshot

![VVS Departures Plugin](screenshot.png)

*Screenshot showing upcoming departures with line number, destination, and departure time*

## Features

- **Real-time departures**: Shows the next 10 departures from your selected station
- **Detailed information**: Displays line number, destination, and departure time
- **Delay indicator**: Visual marker (◯) shows realtime-information
- **Auto-refresh**: Updates every 5 minutes to keep information current
- **Cancelled trips**: Automatically filters out cancelled services
- **Multiple layouts**: Supports full, half (horizontal/vertical), and quadrant display sizes

## Configuration

After installation, you'll need to configure:

- **Station**: Enter the name of your VVS station (e.g., "Hauptbahnhof (Arnulf-Klett-Platz)")
  - Find your station name using the [VVS App](https://www.vvs.de/mobilitaetsapp) or [VVS Website](https://www.vvs.de/)

## How It Works

This plugin fetches departure data from a third-party API (dbf.finalrewind.org) that provides VVS network information. The data includes:

- Line numbers
- Destinations
- Scheduled departure times
- Real-time updates
- Cancellation status

## Development

### Prerequisites

- [trmnlp](https://usetrmnl.com/docs/plugins/development) gem or Docker
- Git

### Local Development

1. Clone the repository:
   ```bash
   git clone https://github.com/hija/trmnl-vvs-abfahrtsplan.git
   cd trmnl-vvs-abfahrtsplan
   ```

2. Configure your station in `.trmnlp.yml`:
   ```yaml
   custom_fields:
     station: 'Your Station Name'
   ```

3. Start the preview server:
   ```bash
   ./bin/trmnlp preview
   ```

4. Open http://localhost:4567 in your browser

### Project Structure

```
.
├── .trmnlp.yml           # Plugin configuration
├── bin/
│   └── trmnlp            # Preview script
└── src/
    ├── settings.yml      # Plugin metadata and custom fields
    ├── full.liquid       # Full screen layout
    ├── half_horizontal.liquid
    ├── half_vertical.liquid
    ├── quadrant.liquid
    └── shared.liquid     # Shared components
```

## Disclaimer

This plugin is **not affiliated** with VVS (Verkehrs- und Tarifverbund Stuttgart). It uses data from a third-party API that may not always be accurate or up-to-date. Please verify critical information with official sources:

- [VVS Website](https://www.vvs.de/)
- [EFA Portal](https://www3.vvs.de/mng/)
- Official VVS App

## Language

The plugin displays information in German, as it is designed specifically for the VVS network in Stuttgart, Germany.

## Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

## License

MIT License - See LICENSE file for details

## Credits

- Data provided by [dbf.finalrewind.org](https://dbf.finalrewind.org/)
- Icon from [Icons8](https://icons8.com/)
- Built for [TRMNL](https://usetrmnl.com/)

## Support

If you encounter any issues or have suggestions:
- Open an issue on [GitHub](https://github.com/hija/trmnl-vvs-abfahrtsplan/issues)
- Check the [TRMNL Documentation](https://usetrmnl.com/docs)
