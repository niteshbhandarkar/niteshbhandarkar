<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Nitesh Bhandarkar - Intune & Cloud Endpoint Notes</title>
    <style>
        * { box-sizing: border-box; margin: 0; padding: 0; }
        body { font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, Helvetica, Arial, sans-serif; line-height: 1.6; color: #1e293b; background-color: #f8fafc; }
        
        /* Header */
        header { background: #1e3a8a; color: white; padding: 2rem 1rem; text-align: center; }
        header h1 { font-size: 2rem; margin-bottom: 0.5rem; }
        header p { color: #93c5fd; font-size: 1rem; }

        /* Navigation / Container */
        .container { max-width: 1100px; margin: 2rem auto; padding: 0 1rem; display: grid; grid-template-columns: 280px 1fr; gap: 2rem; }
        
        @media (max-width: 768px) {
            .container { grid-template-columns: 1fr; }
        }

        /* Sidebar Navigation */
        .sidebar { background: white; padding: 1.5rem; border-radius: 8px; border: 1px solid #e2e8f0; height: fit-content; }
        .sidebar h3 { font-size: 1.1rem; color: #1e3a8a; margin-bottom: 1rem; text-transform: uppercase; border-bottom: 2px solid #3b82f6; padding-bottom: 0.3rem; }
        .sidebar ul { list-style: none; }
        .sidebar li { margin-bottom: 0.8rem; }
        .sidebar a { color: #334155; text-decoration: none; font-weight: 500; display: block; padding: 0.4rem 0.6rem; border-radius: 4px; transition: 0.2s; }
        .sidebar a:hover, .sidebar a.active { background: #eff6ff; color: #2563eb; }

        /* Main Content Area */
        .content { background: white; padding: 2rem; border-radius: 8px; border: 1px solid #e2e8f0; }
        .content h2 { color: #0f172a; margin-bottom: 1rem; border-bottom: 1px solid #e2e8f0; padding-bottom: 0.5rem; }
        .content h3 { color: #1e3a8a; margin: 1.5rem 0 0.5rem 0; }
        
        /* Code & Notes styling */
        pre { background: #0f172a; color: #f8fafc; padding: 1rem; border-radius: 6px; overflow-x: auto; font-size: 0.9rem; margin: 1rem 0; }
        code { background: #f1f5f9; color: #0f172a; padding: 0.2rem 0.4rem; border-radius: 4px; font-size: 0.9rem; }
        .note-box { background: #eff6ff; border-left: 4px solid #2563eb; padding: 1rem; margin: 1rem 0; border-radius: 0 6px 6px 0; }

        footer { text-align: center; padding: 2rem 1rem; color: #64748b; font-size: 0.9rem; margin-top: 2rem; }
    </style>
</head>
<body>

    <header>
        <h1>Intune & Cloud Endpoint Documentation</h1>
        <p>Personal Notes, PowerShell Automation & Interview Preparation | Nitesh Bhandarkar</p>
    </header>

    <div class="container">
        <!-- Sidebar Navigation -->
        <aside class="sidebar">
            <h3>Quick Topics</h3>
            <ul>
                <li><a href="#intune-basics" class="active">1. Intune Core Notes</a></li>
                <li><a href="#autopilot">2. Windows Autopilot</a></li>
                <li><a href="#app-packaging">3. Win32 App Packaging</a></li>
                <li><a href="#sccm-logs">4. SCCM & Intune Logs</a></li>
                <li><a href="#powershell">5. Useful PowerShell Scripts</a></li>
                <li><a href="#interview-qa">6. Interview Q&A (AZ-104)</a></li>
            </ul>
        </aside>

        <!-- Main Content -->
        <main class="content">
            <section id="intune-basics">
                <h2>1. Microsoft Intune Core Concepts</h2>
                <div class="note-box">
                    <strong>Key Focus:</strong> MDM vs MAM policies, Entra ID integration, and Compliance Monitoring.
                </div>
                <h3>Enrollment Methods</h3>
                <ul>
                    <li><strong>BYOD (MAM):</strong> App Protection Policies without full device management.</li>
                    <li><strong>Corporate (MDM):</strong> Full device control, BitLocker enforcement, and Configuration Profiles.</li>
                </ul>
            </section>

            <section id="autopilot" style="margin-top: 2.5rem;">
                <h2>2. Windows Autopilot Setup</h2>
                <p>Zero-touch provisioning framework for deploying out-of-the-box (OOBE) Windows 10/11 devices.</p>
                <h3>Modes:</h3>
                <ul>
                    <li>User-Driven Mode</li>
                    <li>Self-Deploying Mode (Kiosk)</li>
                    <li>Pre-Provisioned Deployment (White Glove)</li>
                </ul>
            </section>

            <section id="sccm-logs" style="margin-top: 2.5rem;">
                <h2>3. Critical Troubleshooting Logs</h2>
                <h3>Intune Client Logs:</h3>
                <code>C:\ProgramData\Microsoft\IntuneManagementExtension\Logs\IntuneManagementExtension.log</code>
                
                <h3>SCCM Core Logs:</h3>
                <ul>
                    <li><code>AppEnforce.log</code> - App Installation & Commands execution</li>
                    <li><code>WUAHandler.log</code> - Patching & WSUS Agent activity</li>
                    <li><code>SMSTS.log</code> - Task Sequence & OSD troubleshooting</li>
                </ul>
            </section>

            <section id="powershell" style="margin-top: 2.5rem;">
                <h2>4. Useful PowerShell Script Snippet</h2>
                <p>Command to fetch Hardware Hash for Windows Autopilot registration:</p>
                <pre><code>Get-WindowsAutoPilotInfo.ps1 -OutputFile C:\Autopilot\HWHash.csv -ConnectSession</code></pre>
            </section>
        </main>
    </div>

    <footer>
        <p>© Nitesh Bhandarkar | Intune & Azure Administrator Notes</p>
    </footer>

</body>
</html>
