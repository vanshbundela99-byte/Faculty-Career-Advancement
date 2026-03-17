import React, { useState } from 'react';

function App() {
  const [page, setPage] = useState('login'); // Simple way to switch pages

  return (
    <div className="App">
      <nav style={{ padding: '10px', background: '#282c34', color: 'white' }}>
        <h1>Faculty Advancement System</h1>
      </nav>

      {page === 'login' ? (
        <Login onLogin={() => setPage('dashboard')} />
      ) : (
        <Dashboard />
      )}
    </div>
  );
}

// Simple Login Component
function Login({ onLogin }) {
  return (
    <div style={{ padding: '20px', textAlign: 'center' }}>
      <h2>Faculty Login</h2>
      <input type="email" placeholder="University Email" /><br/><br/>
      <input type="password" placeholder="Password" /><br/><br/>
      <button onClick={onLogin} style={{ padding: '10px 20px' }}>Login</button>
    </div>
  );
}

// Simple Dashboard Component
function Dashboard() {
  return (
    <div style={{ padding: '20px' }}>
      <h2>Welcome, Professor!</h2>
      <div style={{ border: '1px solid #ccc', padding: '10px', borderRadius: '5px' }}>
        <h3>Your Current API Score: <span style={{ color: 'green' }}>45</span></h3>
        <p>Next Promotion Eligibility: <strong>Associate Professor</strong></p>
        <progress value="45" max="100" style={{ width: '100%' }}></progress>
      </div>
      <br/>
      <button style={{ background: 'blue', color: 'white', padding: '10px' }}>
        + Add New Research Paper
      </button>
    </div>
  );
}

export default App;
