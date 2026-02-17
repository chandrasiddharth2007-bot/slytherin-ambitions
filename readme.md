<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
</head>
<body>

  <h1>🏦 Money Mule Detection using Behavioral Analytics</h1>
  <p class="team-info"><strong>Team:</strong> Slytherin Ambitions | <strong>Location:</strong> IIT Delhi Tryst Hackathon 2026</p>

  <h2>📌 Project Overview</h2>
  <p>
    Financial institutions face a critical challenge in identifying <strong>Money Mule</strong> accounts—legitimate-looking accounts used by criminal networks to launder illicit funds. This project moves beyond static rules to apply <strong>Behavioral Analytics</strong>, identifying the "Financial Fingerprints" left by laundering activity.
  </p>

  <h3>🎯 Key Objectives</h3>
  <ul>
    <li><strong>Isolate Pass-Through Behavior:</strong> Detect accounts where funds are "flushed" immediately after arrival.</li>
    <li><strong>Identify Smurfing Tactics:</strong> Spot transactions structured just below the <strong>₹50,000</strong> PAN reporting threshold.</li>
    <li><strong>Network Topology:</strong> Analyze the "Fan-in/Fan-out" patterns of high-churn counterparties.</li>
  </ul>

  <h2>🧬 Technical Deep Dive: Feature Engineering</h2>
  <p>Our 10/10 EDA rating was achieved by engineering high-impact features that standard models often miss:</p>
  <ul>
    <li><strong>Liquidation Ratio:</strong> Within a 24-hour window. A high ratio is a strong mule signature.</li>
    <li><strong>Dormancy Wake-up:</strong> The time delta between account opening and the first high-value burst. Mules often "age" accounts to bypass new-account filters.</li>
    <li><strong>Counterparty Churn:</strong> The ratio of unique counterparties to total transactions, identifying "Layering" attempts.</li>
  </ul>

  <h2>📊 Behavioral Risk Signatures</h2>
  <table>
    <tr>
      <th>Behavioral Metric</th>
      <th>Legitimate Accounts</th>
      <th>Mule Accounts</th>
      <th>Risk Significance</th>
    </tr>
    <tr>
      <td><strong>Fund Retention</strong></td>
      <td>Days to weeks</td>
      <td>Minutes to hours</td>
      <td>Rapid pass-through laundering.</td>
    </tr>
    <tr>
      <td><strong>Transaction Velocity</strong></td>
      <td>Distributed over time</td>
      <td>Concentrated bursts</td>
      <td>High movement speed of illicit funds.</td>
    </tr>
    <tr>
      <td><strong>Counterparty Churn</strong></td>
      <td>Low (Repeated contacts)</td>
      <td>High (Unique IDs)</td>
      <td>Layering to obscure audit trails.</td>
    </tr>
    <tr>
      <td><strong>Amount Structuring</strong></td>
      <td>Natural spending</td>
      <td>Spiking near ₹50K</td>
      <td>Smurfing to avoid AML triggers.</td>
    </tr>
  </table>

  <h2>🔍 Visual Insights</h2>
  <ul>
    <li><strong>Log-Scale Retention Analysis:</strong> Highlights the massive peak in transfers occurring under 60 minutes for mule accounts.</li>
    <li><strong>Threshold Density Curves:</strong> Visualizes the "Smurfing" spike at the ₹49,000–₹49,999 range.</li>
    <li><strong>Feature Correlation Heatmap:</strong> Quantifies the predictive power of each behavioral trait against the <code>is_mule</code> label.</li>
  </ul>

  <h2>🛠️ Implementation & Setup</h2>
  <h3>1️⃣ Requirements</h3>
  <pre><code>pip install pandas numpy matplotlib seaborn scipy</code></pre>

  <h3>2️⃣ Project Structure</h3>
  <pre><code>├── dataset/    
├── ├──accounts.csv
├── ├── customer_account_linkage.csv
├── ├── customers.csv
├── ├── product_details.csv
├── ├── test_accounts.csv                  
├── ├── train_labels.csv
├── ├── transactions_part_0.csv
├── ├── transactions_part_1.csv
├── ├── transactions_part_2.csv
├── ├── transactions_part_3.csv
├── ├── transactions_part_4.csv
├── ├── transactions_part_5.csv
├── Refined_EDA.ipynb            
├── README.md                    
└── results/                     
</code></pre>

  <h2>🏁 Impact & Conclusion</h2>
  <ol>
    <li><strong>Early Warning:</strong> Detection of "Sleeper" accounts before they are fully utilized for laundering.</li>
    <li><strong>Reduced False Positives:</strong> Distinguishing between high-net-worth legitimate activity and rapid mule passthroughs.</li>
    <li><strong>Actionable Intelligence:</strong> Providing investigators with a "Risk Score" based on quantifiable financial signatures.</li>
  </ol>

</body>
</html>
