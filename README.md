# Salaam-pay-
Money transmitter software 
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Dashboard - Abdul Alim Money Transmitter</title>
    <style>
        body {
            margin: 0;
            padding: 0;
            font-family: 'Arial', sans-serif;
            background-color: #000000;
            color: #C0C0C0;
        }
        
        .container {
            display: flex;
            min-height: 100vh;
        }
        
        .sidebar {
            background-color: #111;
            width: 250px;
            padding: 20px 0;
            flex-shrink: 0;
        }
        
        .sidebar-logo {
            text-align: center;
            padding: 20px;
            border-bottom: 1px solid #333;
            margin-bottom: 20px;
        }
        
        .sidebar-logo h2 {
            font-size: 24px;
            font-weight: 300;
            letter-spacing: 2px;
            margin: 0;
        }
        
        .sidebar-menu {
            list-style-type: none;
            padding: 0;
            margin: 0;
        }
        
        .sidebar-menu li {
            margin-bottom: 5px;
        }
        
        .sidebar-menu a {
            display: flex;
            align-items: center;
            padding: 12px 20px;
            color: #C0C0C0;
            text-decoration: none;
            transition: background-color 0.3s ease;
        }
        
        .sidebar-menu a:hover,
        .sidebar-menu a.active {
            background-color: #222;
        }
        
        .sidebar-menu a i {
            margin-right: 10px;
            width: 20px;
            text-align: center;
        }
        
        .main-content {
            flex-grow: 1;
            padding: 30px;
            overflow-y: auto;
        }
        
        .header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 30px;
        }
        
        .header h1 {
            margin: 0;
            font-size: 28px;
            font-weight: 400;
        }
        
        .user-profile {
            display: flex;
            align-items: center;
        }
        
        .user-profile img {
            width: 40px;
            height: 40px;
            border-radius: 50%;
            margin-right: 10px;
            background-color: #333;
        }
        
        .balance-cards {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(250px, 1fr));
            gap: 20px;
            margin-bottom: 30px;
        }
        
        .balance-card {
            background-color: #111;
            border-radius: 8px;
            padding: 20px;
        }
        
        .balance-card h3 {
            margin-top: 0;
            margin-bottom: 5px;
            font-size: 16px;
            color: #A9A9A9;
        }
        
        .balance-card .amount {
            font-size: 24px;
            font-weight: bold;
            margin-bottom: 10px;
        }
        
        .balance-card .currency {
            font-size: 14px;
            color: #A9A9A9;
        }
        
        .section {
            background-color: #111;
            border-radius: 8px;
            padding: 25px;
            margin-bottom: 30px;
        }
        
        .section h2 {
            margin-top: 0;
            margin-bottom: 20px;
            font-size: 20px;
            font-weight: 500;
        }
        
        .converter-container {
            display: grid;
            grid-template-columns: 1fr auto 1fr;
            gap: 15px;
            align-items: center;
        }
        
        .converter-input {
            display: flex;
            flex-direction: column;
        }
        
        .input-group {
            position: relative;
            margin-bottom: 15px;
        }
        
        .input-group input {
            width: 100%;
            padding: 12px;
            padding-right: 60px;
            background-color: #222;
            border: 1px solid #333;
            border-radius: 4px;
            color: #FFFFFF;
            font-size: 16px;
        }
        
        .input-group input:focus {
            outline: none;
            border-color: #C0C0C0;
        }
        
        .input-group select {
            position: absolute;
            right: 5px;
            top: 50%;
            transform: translateY(-50%);
            background-color: #333;
            border: none;
            color: #C0C0C0;
            padding: 5px;
            border-radius: 3px;
        }
        
        .swap-icon {
            display: flex;
            justify-content: center;
            align-items: center;
            cursor: pointer;
            font-size: 20px;
            color: #C0C0C0;
            background-color: #222;
            width: 40px;
            height: 40px;
            border-radius: 50%;
            transition: background-color 0.3s ease;
        }
        
        .swap-icon:hover {
            background-color: #333;
        }
        
        .btn {
            display: inline-block;
            background-color: #C0C0C0;
            color: #000000;
            padding: 12px 20px;
            border-radius: 4px;
            text-decoration: none;
            font-weight: bold;
            transition: background-color 0.3s ease;
            border: none;
            cursor: pointer;
            margin-top: 15px;
        }
        
        .btn:hover {
            background-color: #A9A9A9;
        }
        
        .conversion-info {
            margin-top: 20px;
            font-size: 14px;
            color: #A9A9A9;
        }
        
        .bitcoin-container {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
            gap: 20px;
        }
        
        .bitcoin-box {
            background-color: #222;
            border-radius: 8px;
            padding: 20px;
            display: flex;
            flex-direction: column;
        }
        
        .bitcoin-price {
            font-size: 24px;
            font-weight: bold;
            margin-bottom: 15px;
        }
        
        .bitcoin-change {
            font-size: 14px;
            margin-bottom: 20px;
        }
        
        .bitcoin-change.positive {
            color: #4CAF50;
        }
        
        .bitcoin-change.negative {
            color: #F44336;
        }
        
        .btn-group {
            display: flex;
            gap: 10px;
        }
        
        .btn-secondary {
            background-color: transparent;
            border: 1px solid #C0C0C0;
            color: #C0C0C0;
        }
        
        .btn-secondary:hover {
            background-color: rgba(192, 192, 192, 0.1);
        }
        
        .transfer-container {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
            gap: 20px;
        }
        
        .transfer-box {
            background-color: #222;
            border-radius: 8px;
            padding: 20px;
        }
        
        .transfer-box h3 {
            margin-top: 0;
            margin-bottom: 15px;
        }
        
        .form-group {
            margin-bottom: 15px;
        }
        
        .form-group label {
            display: block;
            margin-bottom: 5px;
            font-size: 14px;
        }
        
        .form-group input,
        .form-group select {
            width: 100%;
            padding: 10px;
            background-color: #333;
            border: 1px solid #444;
            border-radius: 4px;
            color: #FFFFFF;
        }
        
        .service-fee {
            margin-top: 15px;
            font-size: 14px;
            color: #A9A9A9;
        }
        
        .recent-transactions {
            margin-top: 30px;
        }
        
        .transaction-list {
            list-style-type: none;
            padding: 0;
            margin: 0;
        }
        
        .transaction-item {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 12px 0;
            border-bottom: 1px solid #333;
        }
        
        .transaction-item:last-child {
            border-bottom: none;
        }
        
        .transaction-info {
            display: flex;
            align-items: center;
        }
        
        .transaction-icon {
            width: 36px;
            height: 36px;
            border-radius: 50%;
            background-color: #222;
            display: flex;
            justify-content: center;
            align-items: center;
            margin-right: 15px;
        }
        
        .transaction-details h4 {
            margin: 0;
            font-size: 16px;
            font-weight: 500;
        }
        
        .transaction-details p {
            margin: 5px 0 0;
            font-size: 14px;
            color: #A9A9A9;
        }
        
        .transaction-amount {
            font-weight: bold;
        }
        
        .transaction-amount.positive {
            color: #4CAF50;
        }
        
        .transaction-amount.negative {
            color: #F44336;
        }
        
        @media (max-width: 768px) {
            .container {
                flex-direction: column;
            }
            
            .sidebar {
                width: 100%;
                padding: 10px 0;
            }
            
            .converter-container {
                grid-template-columns: 1fr;
            }
            
            .swap-icon {
                transform: rotate(90deg);
                margin: 10px auto;
            }
        }
    </style>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.1.1/css/all.min.css">
</head>
<body>
    <div class="container">
        <div class="sidebar">
            <div class="sidebar-logo">
                <h2>ABDUL ALIM</h2>
            </div>
            
            <ul class="sidebar-menu">
                <li><a href="#" class="active"><i class="fas fa-home"></i> Dashboard</a></li>
                <li><a href="#"><i class="fas fa-exchange-alt"></i> Currency Exchange</a></li>
                <li><a href="#"><i class="fab fa-bitcoin"></i> Bitcoin</a></li>
                <li><a href="#"><i class="fas fa-paper-plane"></i> Send Money</a></li>
                <li><a href="#"><i class="fas fa-hand-holding-dollar"></i> Receive Money</a></li>
                <li><a href="#"><i class="fas fa-credit-card"></i> Payment Methods</a></li>
                <li><a href="#"><i class="fas fa-history"></i> Transaction History</a></li>
                <li><a href="#"><i class="fas fa-user"></i> Profile</a></li>
                <li><a href="#"><i class="fas fa-cog"></i> Settings</a></li>
                <li><a href="#"><i class="fas fa-headset"></i> Support</a></li>
                <li><a href="index.html"><i class="fas fa-sign-out-alt"></i> Logout</a></li>
            </ul>
        </div>
        
        <div class="main-content">
            <div class="header">
                <h1>Dashboard</h1>
                
                <div class="user-profile">
                    <img src="/api/placeholder/40/40" alt="User Profile">
                    <span>John Doe</span>
                </div>
            </div>
            
            <div class="balance-cards">
                <div class="balance-card">
                    <h3>Total Balance</h3>
                    <div class="amount">$5,230.75</div>
                    <div class="currency">USD</div>
                </div>
                
                <div class="balance-card">
                    <h3>Bitcoin</h3>
                    <div class="amount">0.125 BTC</div>
                    <div class="currency">$4,875.25 USD</div>
                </div>
                
                <div class="balance-card">
                    <h3>Euro</h3>
                    <div class="amount">€320.50</div>
                    <div class="currency">$355.50 USD</div>
                </div>
            </div>
            
            <div class="section">
                <h2>Currency Conversion</h2>
                
                <div class="converter-container">
                    <div class="converter-input">
                        <div class="input-group">
                            <input type="number" id="amountFrom" value="1.00">
                            <select id="currencyFrom">
                                <option value="USD">USD</option>
                                <option value="EUR">EUR</option>
                                <option value="GBP">GBP</option>
                                <option value="JPY">JPY</option>
                                <option value="AUD">AUD</option>
                                <option value="CAD">CAD</option>
                                <option value="CHF">CHF</option>
                                <option value="CNY">CNY</option>
                                <option value="INR">INR</option>
                                <option value="BTC">BTC</option>
                                <!-- Additional currencies would be loaded via API -->
                            </select>
                        </div>
                    </div>
                    
                    <div class="swap-icon" onclick="swapCurrencies()">
                        <i class="fas fa-exchange-alt"></i>
                    </div>
                    
                    <div class="converter-input">
                        <div class="input-group">
                            <input type="number" id="amountTo" value="0.84">
                            <select id="currencyTo">
                                <option value="USD">USD</option>
                                <option value="EUR" selected>EUR</option>
                                <option value="GBP">GBP</option>
                                <option value="JPY">JPY</option>
                                <option value="AUD">AUD</option>
                                <option value="CAD">CAD</option>
                                <option value="CHF">CHF</option>
                                <option value="CNY">CNY</option>
                                <option value="INR">INR</option>
                                <option value="BTC">BTC</option>
                                <!-- Additional currencies would be loaded via API -->
                            </select>
                        </div>
                    </div>
                </div>
                
                <button class="btn" onclick="convertCurrency()">Convert</button>
                
                <div class="conversion-info">
                    <!-- CURRENCY CONVERSION API INTEGRATION GOES HERE -->
                    <!-- Replace this message with actual API integration code -->
                    <p>Exchange Rate: 1 USD = 0.84 EUR</p>
                    <p>Last updated: April 23, 2025 12:30 PM</p>
                    <p><strong>Note:</strong> Integrate currency conversion API here (e.g., ExchangeRate-API, Fixer.io, or Open Exchange Rates)</p>
                </div>
            </div>
            
            <div class="section">
                <h2>Buy & Sell Bitcoin</h2>
                
                <div class="bitcoin-container">
                    <div class="bitcoin-box">
                        <h3>Current Bitcoin Price</h3>
                        <div class="bitcoin-price">$39,876.21</div>
                        <div class="bitcoin-change positive">+2.35% (24h)</div>
                        
                        <div class="btn-group">
                            <button class="btn">Buy Bitcoin</button>
                            <button class="btn btn-secondary">Sell Bitcoin</button>
                        </div>
                    </div>
                    
                    <div class="bitcoin-box">
                        <h3>Your Bitcoin</h3>
                        <div class="bitcoin-price">0.125 BTC</div>
                        <div class="bitcoin-change">$4,875.25 USD</div>
                        
                        <div class="btn-group">
                            <button class="btn">Send</button>
                            <button class="btn btn-secondary">Receive</button>
                        </div>
                    </div>
                </div>
            </div>
            
            <div class="section">
                <h2>Recent Transactions</h2>
                
                <ul class="transaction-list">
                    <li class="transaction-item">
                        <div class="transaction-info">
                            <div class="transaction-icon">
                                <i class="fas fa-arrow-up"></i>
                            </div>
                            <div class="transaction-details">
                                <h4>Sent to Alice Johnson</h4>
                                <p>Apr 20, 2025</p>
                            </div>
                        </div>
                        <div class="transaction-amount negative">-$250.00</div>
                    </li>
                    
                    <li class="transaction-item">
                        <div class="transaction-info">
                            <div class="transaction-icon">
                                <i class="fas fa-arrow-down"></i>
                            </div>
                            <div class="transaction-details">
                                <h4>Received from Bob Smith</h4>
                                <p>Apr 18, 2025</p>
                            </div>
                        </div>
                        <div class="transaction-amount positive">+$450.00</div>
                    </li>
                    
                    <li class="transaction-item">
                        <div class="transaction-info">
                            <div class="transaction-icon">
                                <i class="fab fa-bitcoin"></i>
                            </div>
                            <div class="transaction-details">
                                <h4>Bought Bitcoin</h4>
                                <p>Apr 15, 2025</p>
                            </div>
                        </div>
                        <div class="transaction-amount negative">-$1,000.00</div>
                    </li>
                    
                    <li class="transaction-item">
                        <div class="transaction-info">
                            <div class="transaction-icon">
                                <i class="fas fa-exchange-alt"></i>
                            </div>
                            <div class="transaction-details">
                                <h4>Converted USD to EUR</h4>
                                <p>Apr 10, 2025</p>
                            </div>
                        </div>
                        <div class="transaction-amount">$300.00 → €252.30</div>
                    </li>
                </ul>
            </div>
        </div>
    </div>
    
    <script>
        function swapCurrencies() {
            // Swap currency selection
            const fromCurrency = document.getElementById('currencyFrom').value;
            const toCurrency = document.getElementById('currencyTo').value;
            
            document.getElementById('currencyFrom').value = toCurrency;
            document.getElementById('currencyTo').value = fromCurrency;
            
            // Swap amounts
            const fromAmount = document.getElementById('amountFrom').value;
            const toAmount = document.getElementById('amountTo').value;
            
            document.getE