<html>
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Dual-Channel P-Channel MOSFET Power Switching Circuit</title>
    <script src="https://cdn.jsdelivr.net/npm/react@18.0.0/umd/react.development.js"></script>
    <script src="https://cdn.jsdelivr.net/npm/react-dom@18.0.0/umd/react-dom.development.js"></script>
    <script src="https://cdn.jsdelivr.net/npm/@babel/standalone/babel.js"></script>
    <script src="https://cdn.tailwindcss.com"></script>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/5.15.3/css/all.min.css"></link>
    <link href="https://fonts.googleapis.com/css2?family=Orbitron:wght@400;500;600;700&display=swap" rel="stylesheet">
    <style>
        body {
            font-family: 'Arial', sans-serif;
            background-color: #0f172a;
            color: #e2e8f0;
        }
        .orbitron {
            font-family: 'Orbitron', sans-serif;
        }
        .glow-text {
            text-shadow: 0 0 10px rgba(0, 194, 203, 0.7);
        }
        .pulse-animation {
            animation: pulse 2s infinite;
        }
        @keyframes pulse {
            0%, 100% { opacity: 1; }
            50% { opacity: 0.7; }
        }
        .blink-cursor {
            animation: blink 1s step-end infinite;
        }
        @keyframes blink {
            from, to { border-color: transparent; }
            50% { border-color: white; }
        }
    </style>
</head>
<body>
    <div id="root"></div>

    <script type="text/babel">
        const App = () => {
            return (
                <div className="min-h-screen bg-gray-900 text-white p-4">
                    {/* Header with animated title */}
                    <header className="mb-8">
                        <h1 className="text-center orbitron text-3xl md:text-4xl mb-4">
                            <span className="text-yellow-400">⚡</span> 
                            Dual-Channel P-Channel MOSFET Power Switching Circuit 
                            <span className="text-yellow-400">⚡</span>
                        </h1>
                        <div className="flex justify-center items-center h-12 overflow-hidden">
                            <div className="animate-pulse flex space-x-2">
                                {[...Array(3)].map((_, i) => (
                                    <div key={i} className={`w-2 h-2 rounded-full ${i === 0 ? 'bg-red-500' : i === 1 ? 'bg-green-500' : 'bg-blue-500'}`}></div>
                                ))}
                            </div>
                        </div>
                    </header>

                    <main className="max-w-4xl mx-auto">
                        {/* Overview Section */}
                        <section className="mb-8">
                            <h2 className="text-xl font-bold mb-3 text-teal-300">📘 Overview</h2>
                            <p className="text-gray-300 leading-relaxed">
                                The <strong>Dual-Channel P-Channel MOSFET Power Switching Circuit</strong> ensures <strong>instantaneous and seamless power transfer</strong> between primary (adapter) and backup (battery) sources.
                                <br /><br />
                                This MOSFET-based design achieves <strong>zero switching delay</strong>, offering <strong>reliable and efficient power management</strong> for embedded and IoT systems.
                            </p>
                            <p className="text-gray-300 mt-2">
                                This circuit eliminates mechanical relays, ensuring <strong>noise-free, fast switching</strong>, and <strong>continuous power delivery</strong> to sensitive electronic systems.
                            </p>
                        </section>

                        {/* Key Features Section */}
                        <section className="mb-8">
                            <h2 className="text-xl font-bold mb-3 text-teal-300">⚙️ Key Features</h2>
                            <ul className="list-disc pl-6 space-y-2 text-gray-300">
                                <li><strong>⚡ MOSFET-based high-side switching</strong> – instant power handover without relays</li>
                                <li><strong>🔋 Dual power inputs</strong> (24 V adapter + 7.6 V battery) with automatic priority handling</li>
                                <li><strong>🔄 Zero-delay switching</strong> using DMP4025LK3 MOSFETs</li>
                                <li><strong>🧲 Reverse current protection</strong> via Schottky diodes (B540C)</li>
                                <li><strong>🧠 Stability ensured</strong> using RC gate damping networks</li>
                                <li><strong>🧩 Compact PCB-ready design</strong> simulated in LTspice and designed in Altium Designer</li>
                            </ul>
                        </section>

                        {/* Circuit Overview Section */}
                        <section className="mb-8">
                            <h2 className="text-xl font-bold mb-3 text-teal-300">🧠 Circuit Overview</h2>
                            <p className="text-gray-300 mb-4">
                                The design uses two P-channel MOSFETs (<strong>M1</strong>, <strong>M2</strong>) for automatic high-side switching.
                            </p>
                            <p className="text-gray-300 mb-2">
                                - When the 24 V source is active, <strong>M1</strong> conducts and powers the load.
                            </p>
                            <p className="text-gray-300 mb-2">
                                - If the adapter supply fails, <strong>M1</strong> turns off and <strong>M2</strong> (connected to the 7.6 V battery) activates instantly.
                            </p>
                            <p className="text-gray-300 mb-2">
                                - <strong>Diodes D1 and D2 (B540C)</strong> block reverse current and protect the sources.
                            </p>
                            <p className="text-gray-300">
                                - <strong>C1–C3</strong> capacitors stabilize voltage transients ensuring clean output.
                            </p>
                            
                            <div className="mt-4 flex justify-center">
                                <img src="https://placehold.co/800x300/e2e8f0/374151?text=Circuit+Schematic" alt="Circuit schematic showing two P-channel MOSFETs (M1 and M2), Schottky diodes (D1 and D2), resistors, capacitors, and power connections between 24V adapter, 7.6V battery, and load" className="rounded-lg shadow-lg max-w-full h-auto" />
                            </div>
                        </section>

                        {/* Components Section */}
                        <section className="mb-8">
                            <h2 className="text-xl font-bold mb-3 text-teal-300">🧩 Components Used</h2>
                            <div className="overflow-x-auto">
                                <table className="min-w-full bg-gray-800 rounded-lg overflow-hidden">
                                    <thead>
                                        <tr className="bg-gray-700">
                                            <th className="py-2 px-4 text-left">Component</th>
                                            <th className="py-2 px-4 text-left">Description</th>
                                            <th className="py-2 px-4 text-left">Quantity</th>
                                        </tr>
                                    </thead>
                                    <tbody>
                                        <tr className="border-b border-gray-700">
                                            <td className="py-2 px-4">DMP4025LK3</td>
                                            <td className="py-2 px-4">P-Channel Power MOSFET</td>
                                            <td className="py-2 px-4">2</td>
                                        </tr>
                                        <tr className="border-b border-gray-700">
                                            <td className="py-2 px-4">B540C</td>
                                            <td className="py-2 px-4">Schottky Diode</td>
                                            <td className="py-2 px-4">2</td>
                                        </tr>
                                        <tr className="border-b border-gray-700">
                                            <td className="py-2 px-4">R1, R2</td>
                                            <td className="py-2 px-4">4.7 kΩ Resistors</td>
                                            <td className="py-2 px-4">2</td>
                                        </tr>
                                        <tr className="border-b border-gray-700">
                                            <td className="py-2 px-4">C1, C2</td>
                                            <td className="py-2 px-4">10 µF Capacitors</td>
                                            <td className="py-2 px-4">2</td>
                                        </tr>
                                        <tr className="border-b border-gray-700">
                                            <td className="py-2 px-4">C3</td>
                                            <td className="py-2 px-4">1 µF Capacitor</td>
                                            <td className="py-2 px-4">1</td>
                                        </tr>
                                        <tr className="border-b border-gray-700">
                                            <td className="py-2 px-4">V1</td>
                                            <td className="py-2 px-4">24 V DC Supply</td>
                                            <td className="py-2 px-4">1</td>
                                        </tr>
                                        <tr className="border-b border-gray-700">
                                            <td className="py-2 px-4">V3</td>
                                            <td className="py-2 px-4">7.6 V Battery</td>
                                            <td className="py-2 px-4">1</td>
                                        </tr>
                                        <tr>
                                            <td className="py-2 px-4">Load</td>
                                            <td className="py-2 px-4">50 Ω Resistive Load</td>
                                            <td className="py-2 px-4">1</td>
                                        </tr>
                                    </tbody>
                                </table>
                            </div>
                        </section>

                        {/* Tools & Simulation Section */}
                        <section className="mb-8">
                            <h2 className="text-xl font-bold mb-3 text-teal-300">🧰 Tools & Simulation</h2>
                            <div className="flex flex-wrap gap-2 mb-4">
                                <div className="bg-gray-700 px-4 py-2 rounded-md flex items-center">
                                    <i className="fab fa-linux mr-2"></i>
                                    <span>LTspice</span>
                                </div>
                                <div className="bg-gray-700 px-4 py-2 rounded-md flex items-center">
                                    <i className="fas fa-microchip mr-2"></i>
                                    <span>Altium Designer</span>
                                </div>
                                <div className="bg-gray-700 px-4 py-2 rounded-md flex items-center">
                                    <i className="fas fa-tools mr-2"></i>
                                    <span>Electronics Hardware Design</span>
                                </div>
                            </div>
                            <p className="text-gray-300">
                                - <strong>Simulation Tool:</strong> LTspice (for transient switching, delay, and voltage drop analysis)
                            </p>
                            <p className="text-gray-300">
                                - <strong>PCB Design Tool:</strong> Altium Designer (layout optimization, component routing, and thermal considerations)
                            </p>
                            <p className="text-gray-300">
                                - <strong>Validation:</strong> Bench-tested with oscilloscope to ensure uninterrupted power delivery
                            </p>
                        </section>

                        {/* Repository Files Section */}
                        <section className="mb-8">
                            <h2 className="text-xl font-bold mb-3 text-teal-300">🧾 Repository Files</h2>
                            <div className="overflow-x-auto">
                                <table className="min-w-full bg-gray-800 rounded-lg overflow-hidden">
                                    <thead>
                                        <tr className="bg-gray-700">
                                            <th className="py-2 px-4 text-left">File</th>
                                            <th className="py-2 px-4 text-left">Description</th>
                                        </tr>
                                    </thead>
                                    <tbody>
                                        <tr className="border-b border-gray-700">
                                            <td className="py-2 px-4">schematic.png</td>
                                            <td className="py-2 px-4">Circuit schematic image</td>
                                        </tr>
                                        <tr className="border-b border-gray-700">
                                            <td className="py-2 px-4">Dual_Power_Switching_Circuit.asc</td>
                                            <td className="py-2 px-4">LTspice simulation file</td>
                                        </tr>
                                        <tr className="border-b border-gray-700">
                                            <td className="py-2 px-4">report.pdf</td>
                                            <td className="py-2 px-4">Detailed design and analysis report</td>
                                        </tr>
                                        <tr className="border-b border-gray-700">
                                            <td className="py-2 px-4">index.html</td>
                                            <td className="py-2 px-4">Interactive project landing page</td>
                                        </tr>
                                        <tr>
                                            <td className="py-2 px-4">datasheet/</td>
                                            <td className="py-2 px-4">Component datasheets and PCB files</td>
                                        </tr>
                                    </tbody>
                                </table>
                            </div>
                        </section>

                        {/* Project Report Section */}
                        <section className="mb-8">
                            <h2 className="text-xl font-bold mb-3 text-teal-300">📄 Project Report</h2>
                            <p className="text-gray-300">
                                📘 <a href="#" className="text-blue-400 hover:text-blue-300 underline">View Full Report (PDF)</a>
                            </p>
                        </section>

                        {/* Applications Section */}
                        <section className="mb-8">
                            <h2 className="text-xl font-bold mb-3 text-teal-300">🧪 Applications</h2>
                            <ul className="list-disc pl-6 space-y-2 text-gray-300">
                                <li>Industrial Energy Monitoring Systems (IEMS)</li>
                                <li>Embedded IoT Devices</li>
                                <li>Solar and Battery Power Systems</li>
                                <li>UPS and Backup Power Units</li>
                                <li>Portable Sensor Hubs</li>
                            </ul>
                        </section>

                        {/* Simulation Snapshot Section */}
                        <section className="mb-8">
                            <h2 className="text-xl font-bold mb-3 text-teal-300">📈 Simulation Snapshot</h2>
                            <div className="flex justify-center">
                                <img src="https://placehold.co/800x300/e2e8f0/374151?text=Simulation+Waveform" alt="Simulation waveform showing smooth transition between 24V adapter and 7.6V battery power sources with zero delay" className="rounded-lg shadow-lg max-w-full h-auto" />
                            </div>
                        </section>

                        {/* Author Section */}
                        <section className="mb-8">
                            <h2 className="text-xl font-bold mb-3 text-teal-300">👨‍💻 Author</h2>
                            <p className="text-gray-300 mb-2">
                                <strong>Pramodh R S</strong>
                            </p>
                            <p className="text-gray-300 mb-4">
                                Embedded Systems Engineer – PHYTEC Embedded Pvt. Ltd, Bengaluru
                            </p>
                            <p className="text-gray-300 mb-2">
                                📬 <strong>Contact:</strong>
                            </p>
                            <div className="flex flex-wrap gap-3">
                                <a href="mailto:rspramodh5@gmail.com" className="bg-gray-700 hover:bg-gray-600 px-4 py-2 rounded-md flex items-center transition duration-300">
                                    <i className="far fa-envelope mr-2"></i>
                                    Email
                                </a>
                                <a href="#" className="bg-gray-700 hover:bg-gray-600 px-4 py-2 rounded-md flex items-center transition duration-300">
                                    <i className="fab fa-linkedin mr-2"></i>
                                    LinkedIn
                                </a>
                                <a href="#" className="bg-gray-700 hover:bg-gray-600 px-4 py-2 rounded-md flex items-center transition duration-300">
                                    <i className="fab fa-github mr-2"></i>
                                    GitHub
                                </a>
                            </div>
                        </section>

                        {/* License Section */}
                        <section className="mb-8">
                            <h2 className="text-xl font-bold mb-3 text-teal-300">⚙️ License</h2>
                            <p className="text-gray-300">
                                This project is open-source under the <strong>MIT License</strong>. Feel free to use, modify, and improve the design with attribution.
                            </p>
                        </section>

                        {/* Acknowledgments Section */}
                        <section className="mb-8">
                            <h2 className="text-xl font-bold mb-3 text-teal-300">⭐ Acknowledgments</h2>
                            <p className="text-gray-300">
                                Special thanks to <strong>PHYTEC Embedded Pvt. Ltd</strong> for providing hardware and development support, and to the embedded design community for sharing valuable MOSFET switching resources.
                            </p>
                        </section>
                    </main>
                </div>
            );
        };

        ReactDOM.render(<App />, document.getElementById('root'));
    </script>
</body>
</html>
