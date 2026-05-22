# StupidoPrint 🖨️

A web-based printing interface for CUPS-enabled Linux systems. StupidoPrint provides a browser-based solution for local and network printing without requiring driver installation or complex configuration on client devices.

## Features

- **Browser-based interface** - No software installation on client devices
- **Drag-and-drop file upload** - Simple file handling for PDFs and images
- **Print preview** - Visual preview before sending to printer
- **Configurable print settings** - Paper size, quality, color mode, scaling, and rotation
- **Network access** - Host on local network for access across devices
- **CUPS integration** - Works with existing printer configurations

## Supported File Types

- PDF documents
- Images: JPG, PNG, GIF, BMP, WebP

## Deployment

### Local Kiosk Setup

```bash
make show
```

Access the interface at `http://localhost:4173`

### Network Setup

```bash
make run-network
```

The application will display the network URL for sharing across devices.

## Prerequisites

- Linux system with CUPS printer support
- Node.js 18 or higher
- Connected and configured printer

## Installation

```bash
git clone https://github.com/schurawel/StupidioPrint.git
cd StupidioPrint

chmod +x config_printer.sh
./config_printer.sh

make install
make run-network
```

## Configuration

### Printer Configuration

Run the configuration script to detect and configure available printers:

```bash
./config_printer.sh
```

### Print Options

Users can configure:

- **Paper Size**: A4, A3, Letter, Legal
- **Print Quality**: Draft, Normal, High
- **Color Mode**: Color, Grayscale, Black & White
- **Duplex**: Single-sided, double-sided horizontal, double-sided vertical
- **Copies**: 1-10
- **Page Layout**: 1, 2, 4, 6, 8, 9, 12, or 16 pages per sheet
- **Scaling**: 10%-200%
- **Rotation**: 0°, 90°, 180°, 270°
- **Page Range**: All pages or specific ranges

Modify the source code to adjust available user options.

## Troubleshooting

### Printer Not Found

```bash
./config_printer.sh
```

### Cannot Access from Network

- Verify firewall allows ports 3001 and 4173
- Confirm devices are on the same network
- Check host computer firewall settings

### File Upload Issues

- Verify file size is within limits (default: 50MB)
- Confirm file type is supported
- Clear browser cache and retry

### Print Job Failures

- Verify printer is powered on and has supplies
- Check CUPS status: `lpstat -p`
- Re-run printer configuration

## Development

### Contributing

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/name`)
3. Commit changes (`git commit -m 'Description'`)
4. Push to branch (`git push origin feature/name`)
5. Open a Pull Request

## License

MIT License - see [LICENSE](LICENSE) file for details
