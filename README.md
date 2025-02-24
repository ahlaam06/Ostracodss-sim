# Ostracodss-sim
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Ostracod Bioluminescence Simulation</title>
    <script src="https://cdn.jsdelivr.net/npm/chart.js"></script>
    <style>
        body { font-family: Arial, sans-serif; text-align: center; }
        canvas { max-width: 600px; margin: 20px auto; }
    </style>
</head>
<body>
    <h1>Ostracod Bioluminescence Simulation</h1>
    <p>Tracking bioluminescent courtship displays under different LED intensities</p>
    <canvas id="bioluminescenceChart"></canvas>
    
    <script>
        const weeks = [1, 2, 3];
        const controlData = [100, 95, 90]; // No LED
        const lowLEDData = [100, 85, 70]; // Low Intensity LED
        const highLEDData = [100, 60, 30]; // High Intensity LED

        const ctx = document.getElementById('bioluminescenceChart').getContext('2d');
        new Chart(ctx, {
            type: 'line',
            data: {
                labels: weeks.map(w => `Week ${w}`),
                datasets: [
                    {
                        label: 'Control (No LED)',
                        data: controlData,
                        borderColor: 'green',
                        fill: false
                    },
                    {
                        label: 'Low Intensity LED',
                        data: lowLEDData,
                        borderColor: 'blue',
                        fill: false
                    },
                    {
                        label: 'High Intensity LED',
                        data: highLEDData,
                        borderColor: 'red',
                        fill: false
                    }
                ]
            },
            options: {
                responsive: true,
                plugins: {
                    legend: { position: 'top' }
                },
                scales: {
                    y: { beginAtZero: true, title: { display: true, text: 'Bioluminescence Activity (%)' } },
                    x: { title: { display: true, text: 'Weeks' } }
                }
            }
        });
    </script>
</body>
</html>
