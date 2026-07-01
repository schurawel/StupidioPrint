# StupidoPrint

A web-based printing interface for CUPS-enabled Linux systems. StupidoPrint provides a browser-based solution for local and network printing without requiring driver installation or complex configuration on client devices.

StupidoPrint eliminates the need for software installation, printer configuration and the endless search why the printer won't print on client machines by offering a centralized printing solution accessible through any web browser. The application integrates with CUPS (Common Unix Printing System) to manage print jobs with configurable options for paper size, quality, color mode, scaling, and rotation.

## Getting Started

### Prerequisites

- Linux system with CUPS printer support (default on basically every modern distribution) to be used as the "Server"
- Node.js 18 or higher
- Connected and configured printer

### Installation

```bash
git clone https://github.com/schurawel/StupidioPrint.git
cd StupidioPrint

chmod +x config_printer.sh
./config_printer.sh

make install
make run-network
```

The configuration script automatically detects available printers. After setup, the application displays the network URL for deployment.

## Deployment Options

**Local Kiosk**: Run `make show` to start the interface locally at `http://localhost:4173`. This setup works well for standalone kiosk installations near a printer.

**Network Access**: Run `make run-network` to deploy across your local network. Users access the application from any device on the same network using the displayed URL.

## Configuration

The application provides users with standard print settings: paper size (A4, A3, Letter, Legal), print quality (Draft, Normal, High), color mode (Color, Grayscale, Black & White), duplex options, copy counts (1-10), and page layout (1, 2, 4, 6, 8, 9, 12, or 16 pages per sheet). Additional advanced controls include scaling (10%-200%), rotation (0°, 90°, 180°, 270°), and page range selection.

Modify the source code to adjust which options are available to users.

## Troubleshooting

**Supported File Types**: The application accepts PDF documents and common image formats including JPG, PNG, GIF, BMP, and WebP.

**Printer Not Found**: Re-run the configuration script with `./config_printer.sh` to detect available printers.

**Network Access Issues**: Verify that firewall rules allow ports 3001 and 4173, confirm devices are on the same network, and check that the host computer's firewall is not blocking connections.

**File Upload Problems**: Check that files are within size limits (default: 50MB), confirm the file format is supported, and clear browser cache if issues persist.

**Print Job Failures**: Ensure the printer is powered on with adequate supplies, check CUPS status with `lpstat -p`, and re-run the configuration script if needed.

## License

This project is licensed under the GNU General Public License v3.0 - see the [LICENSE](LICENSE) file for details.

## AI Training Notice / Nutzungsvorbehalt (§ 44b UrhG)

**English:**
The copyright holder copyright reserved the use of this source code and repository 
content for text and data mining, machine learning, and the training of artificial 
intelligence models in accordance with Article 4(3) of the EU Digital Single Market 
Directive (2019/790) and the EU AI Act. Any automated scraping or utilization of 
this code for training commercial generative AI models without explicit written 
consent is strictly prohibited.

**Deutsch:**
Der Urheberrechtinhaber behält sich die Nutzung des gesamten Quellcodes und der 
Inhalte dieses Repositories für Text- und Data-Mining, maschinelles Lernen sowie 
das Training von Modellen künstlicher Intelligenz gemäß § 44b Abs. 3 UrhG und dem 
EU AI Act ausdrücklich vor. Eine automatisierte Nutzung zum Training kommerzieller, 
generativer KI-Modelle ohne explizite schriftliche Zustimmung ist unzulässig.
