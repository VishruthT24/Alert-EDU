<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Alert EDU</title>
    <script defer src="https://cdn.jsdelivr.net/npm/react@17/umd/react.development.js"></script>
    <script defer src="https://cdn.jsdelivr.net/npm/react-dom@17/umd/react-dom.development.js"></script>
    <script defer src="https://cdn.jsdelivr.net/npm/@babel/standalone/babel.min.js"></script>
    <script defer src="https://maps.googleapis.com/maps/api/js?key=YOUR_API_KEY&libraries=places"></script>
    <style>
        body { font-family: Arial, sans-serif; background-color: #e3f2fd; margin: 0; padding: 20px; }
        .container { max-width: 800px; margin: auto; padding: 20px; background: white; border-radius: 10px; box-shadow: 0 4px 8px rgba(0, 0, 0, 0.2); }
        h1, h2 { color: #1565c0; }
        .section { margin-bottom: 20px; padding: 15px; border-radius: 8px; background: #bbdefb; }
        .alert { border: 1px solid #1565c0; padding: 10px; margin-top: 10px; border-radius: 5px; }
        input, textarea, button, select { display: block; width: 100%; margin-top: 10px; padding: 10px; }
        button { background: #1565c0; color: white; border: none; cursor: pointer; }
        button:hover { background: #0d47a1; }
        .tabs { display: flex; justify-content: space-around; margin-bottom: 20px; }
        .tabs button { padding: 10px 20px; background: #1565c0; color: white; border: none; cursor: pointer; border-radius: 5px; }
        .tabs button:hover { background: #0d47a1; }
        .tabs button.active { background: #0d47a1; }
    </style>
    <script defer type="text/babel">
        function LoginPage({ onLogin }) {
            const [email, setEmail] = React.useState("");
            const [password, setPassword] = React.useState("");
            
            const handleLogin = (e) => {
                e.preventDefault();
                if (email.endsWith("@cobbk12.org")) {
                    onLogin("admin");
                } else if (email.endsWith("@students.cobbk12.org")) {
                    onLogin("user");
                } else {
                    alert("Invalid email domain");
                }
            };
            
            return (
                <div className="container">
                    <h1>Login to Alert EDU</h1>
                    <form onSubmit={handleLogin}>
                        <input type="email" placeholder="Email" value={email} onChange={(e) => setEmail(e.target.value)} />
                        <input type="password" placeholder="Password" value={password} onChange={(e) => setPassword(e.target.value)} />
                        <button type="submit">Login</button>
                    </form>
                </div>
            );
        }
        
        function AlertEdu() {
            const [alerts, setAlerts] = React.useState([]);
            const [newAlert, setNewAlert] = React.useState({ title: "", message: "", type: "school", location: "" });
            const [pendingAlerts, setPendingAlerts] = React.useState([]);
            const [isLoggedIn, setIsLoggedIn] = React.useState(false);
            const [userRole, setUserRole] = React.useState(null);
            const [activeTab, setActiveTab] = React.useState("view");

            React.useEffect(() => {
                const autocomplete = new google.maps.places.Autocomplete(document.getElementById("location-input"));
                autocomplete.addListener("place_changed", () => {
                    const place = autocomplete.getPlace();
                    setNewAlert(prev => ({ ...prev, location: place.formatted_address }));
                });
            }, []);
            
            const handleSubmit = (e) => {
                e.preventDefault();
                if (newAlert.title && newAlert.message) {
                    if (userRole === "admin") {
                        setAlerts([...alerts, { id: alerts.length + 1, ...newAlert, verified: true }]);
                    } else {
                        setPendingAlerts([...pendingAlerts, { id: pendingAlerts.length + 1, ...newAlert, verified: false }]);
                    }
                    setNewAlert({ title: "", message: "", type: "school", location: "" });
                }
            };
            
            const handleVerify = (id) => {
                if (userRole !== "admin") return;
                const alertToVerify = pendingAlerts.find(alert => alert.id === id);
                if (alertToVerify) {
                    setAlerts([...alerts, { ...alertToVerify, verified: true }]);
                    setPendingAlerts(pendingAlerts.filter(alert => alert.id !== id));
                }
            };

            const renderTabContent = () => {
                switch(activeTab) {
                    case "submit":
                        return (
                            <div className="section">
                                <h2>Submit an Alert</h2>
                                <form onSubmit={handleSubmit}>
                                    <input type="text" placeholder="Alert Title" value={newAlert.title} onChange={(e) => setNewAlert({ ...newAlert, title: e.target.value })} />
                                    <textarea placeholder="Alert Message" value={newAlert.message} onChange={(e) => setNewAlert({ ...newAlert, message: e.target.value })}></textarea>
                                    <input id="location-input" type="text" placeholder="Enter Location" value={newAlert.location} readOnly />
                                    <select value={newAlert.type} onChange={(e) => setNewAlert({ ...newAlert, type: e.target.value })}>
                                        <option value="school">School Wide</option>
                                        <option value="county">County Wide</option>
                                    </select>
                                    <button type="submit">{userRole === "admin" ? "Post Alert" : "Submit for Verification"}</button>
                                </form>
                            </div>
                        );
                    case "pending":
                        return userRole === "admin" ? (
                            <div className="section">
                                <h2>Pending Alerts (Admin Verification)</h2>
                                {pendingAlerts.length > 0 ? pendingAlerts.map(alert => (
                                    <div key={alert.id} className="alert">
                                        <h4>{alert.title}</h4>
                                        <p>{alert.message}</p>
                                        <p><strong>Location:</strong> {alert.location}</p>
                                        <button onClick={() => handleVerify(alert.id)}>Verify</button>
                                    </div>
                                )) : <p>No pending alerts.</p>}
                            </div>
                        ) : null;
                    case "view":
                        return (
                            <div className="section">
                                <h2>View Alerts</h2>
                                {alerts.length > 0 ? alerts.map(alert => (
                                    <div key={alert.id} className="alert">
                                        <h4>{alert.title}</h4>
                                        <p>{alert.message}</p>
                                        <p><strong>Location:</strong> {alert.location}</p>
                                    </div>
                                )) : <p>No alerts available.</p>}
                            </div>
                        );
                    case "contact":
                        return (
                            <div className="section">
                                <h2>Contact Information</h2>
                                <p><strong>Counselor Hotline:</strong> (123) 456-7890</p>
                                <p><strong>Admin Hotline:</strong> (987) 654-3210</p>
                            </div>
                        );
                    default:
                        return null;
                }
            };
            
            if (!isLoggedIn) {
                return <LoginPage onLogin={(role) => { setUserRole(role); setIsLoggedIn(true); }} />;
            }

            return (
                <div className="container">
                    <h1>Alert EDU</h1>
                    <div className="tabs">
                        <button onClick={() => setActiveTab("submit")} className={activeTab === "submit" ? "active" : ""}>Submit Alert</button>
                        {userRole === "admin" && <button onClick={() => setActiveTab("pending")} className={activeTab === "pending" ? "active" : ""}>Pending Alerts</button>}
                        <button onClick={() => setActiveTab("view")} className={activeTab === "view" ? "active" : ""}>View Alerts</button>
                        <button onClick={() => setActiveTab("contact")} className={activeTab === "contact" ? "active" : ""}>Contact Info</button>
                    </div>
                    {renderTabContent()}
                </div>
            );
        }
        ReactDOM.render(<AlertEdu />, document.getElementById("root"));
    </script>
</head>
<body>
    <div id="root"></div>
</body>
</html>
