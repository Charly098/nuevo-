<html><head><base href="."</head>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Encuesta Empresarial</title>
    <script src="https://cdn.jsdelivr.net/npm/chart.js"></script>
    <style>
        body {
            font-family: Arial, sans-serif;
            max-width: 800px;
            margin: 0 auto;
            padding: 20px;
            background-color: #f5f5f5;
        }
        .survey-container {
            background-color: white;
            padding: 20px;
            border-radius: 10px;
            box-shadow: 0 0 10px rgba(0,0,0,0.1);
        }
        .question {
            margin-bottom: 20px;
            padding: 15px;
            border: 1px solid #ddd;
            border-radius: 5px;
        }
        .options {
            margin-left: 20px;
        }
        button {
            background-color: #4CAF50;
            color: white;
            padding: 10px 20px;
            border: none;
            border-radius: 5px;
            cursor: pointer;
            font-size: 16px;
            margin-top: 20px;
        }
        button:hover {
            background-color: #45a049;
        }
        #results {
            margin-top: 20px;
            display: none;
        }
        .chart-container {
            width: 100%;
            max-width: 600px;
            margin: 20px auto;
        }
    </style>
</head>
<body>
    <div class="survey-container">
        <h1>Encuesta de Satisfacción Laboral</h1>
        <form id="surveyForm">
            <div class="question">
                <p>1. ¿Qué tan satisfecho está con su ambiente laboral?</p>
                <div class="options">
                    <input type="radio" name="q1" value="Muy satisfecho" required> Muy satisfecho<br>
                    <input type="radio" name="q1" value="Satisfecho"> Satisfecho<br>
                    <input type="radio" name="q1" value="Neutral"> Neutral<br>
                    <input type="radio" name="q1" value="Insatisfecho"> Insatisfecho
                </div>
            </div>

            <div class="question">
                <p>2. ¿Cómo calificaría la comunicación con su supervisor directo?</p>
                <div class="options">
                    <input type="radio" name="q2" value="Excelente" required> Excelente<br>
                    <input type="radio" name="q2" value="Buena"> Buena<br>
                    <input type="radio" name="q2" value="Regular"> Regular<br>
                    <input type="radio" name="q2" value="Mala"> Mala
                </div>
            </div>

            <div class="question">
                <p>3. ¿Considera que tiene oportunidades de crecimiento en la empresa?</p>
                <div class="options">
                    <input type="radio" name="q3" value="Definitivamente sí" required> Definitivamente sí<br>
                    <input type="radio" name="q3" value="Probablemente sí"> Probablemente sí<br>
                    <input type="radio" name="q3" value="Probablemente no"> Probablemente no<br>
                    <input type="radio" name="q3" value="Definitivamente no"> Definitivamente no
                </div>
            </div>

            <div class="question">
                <p>4. ¿Qué tan equilibrada considera su vida laboral y personal?</p>
                <div class="options">
                    <input type="radio" name="q4" value="Muy equilibrada" required> Muy equilibrada<br>
                    <input type="radio" name="q4" value="Equilibrada"> Equilibrada<br>
                    <input type="radio" name="q4" value="Poco equilibrada"> Poco equilibrada<br>
                    <input type="radio" name="q4" value="Nada equilibrada"> Nada equilibrada
                </div>
            </div>

            <div class="question">
                <p>5. ¿Las herramientas proporcionadas son adecuadas para su trabajo?</p>
                <div class="options">
                    <input type="radio" name="q5" value="Totalmente adecuadas" required> Totalmente adecuadas<br>
                    <input type="radio" name="q5" value="Adecuadas"> Adecuadas<br>
                    <input type="radio" name="q5" value="Poco adecuadas"> Poco adecuadas<br>
                    <input type="radio" name="q5" value="Inadecuadas"> Inadecuadas
                </div>
            </div>

            <div class="question">
                <p>6. ¿Cómo califica el trabajo en equipo en su departamento?</p>
                <div class="options">
                    <input type="radio" name="q6" value="Excelente" required> Excelente<br>
                    <input type="radio" name="q6" value="Bueno"> Bueno<br>
                    <input type="radio" name="q6" value="Regular"> Regular<br>
                    <input type="radio" name="q6" value="Malo"> Malo
                </div>
            </div>

            <div class="question">
                <p>7. ¿Qué tan claros son los objetivos de su puesto?</p>
                <div class="options">
                    <input type="radio" name="q7" value="Muy claros" required> Muy claros<br>
                    <input type="radio" name="q7" value="Claros"> Claros<br>
                    <input type="radio" name="q7" value="Poco claros"> Poco claros<br>
                    <input type="radio" name="q7" value="Nada claros"> Nada claros
                </div>
            </div>

            <div class="question">
                <p>8. ¿Considera que su trabajo es reconocido y valorado?</p>
                <div class="options">
                    <input type="radio" name="q8" value="Siempre" required> Siempre<br>
                    <input type="radio" name="q8" value="Frecuentemente"> Frecuentemente<br>
                    <input type="radio" name="q8" value="Ocasionalmente"> Ocasionalmente<br>
                    <input type="radio" name="q8" value="Nunca"> Nunca
                </div>
            </div>

            <div class="question">
                <p>9. ¿Qué tan satisfecho está con los beneficios que ofrece la empresa?</p>
                <div class="options">
                    <input type="radio" name="q9" value="Muy satisfecho" required> Muy satisfecho<br>
                    <input type="radio" name="q9" value="Satisfecho"> Satisfecho<br>
                    <input type="radio" name="q9" value="Poco satisfecho"> Poco satisfecho<br>
                    <input type="radio" name="q9" value="Insatisfecho"> Insatisfecho
                </div>
            </div>

            <div class="question">
                <p>10. ¿Recomendaría esta empresa como lugar para trabajar?</p>
                <div class="options">
                    <input type="radio" name="q10" value="Definitivamente sí" required> Definitivamente sí<br>
                    <input type="radio" name="q10" value="Probablemente sí"> Probablemente sí<br>
                    <input type="radio" name="q10" value="Probablemente no"> Probablemente no<br>
                    <input type="radio" name="q10" value="Definitivamente no"> Definitivamente no
                </div>
            </div>

            <button type="submit">Enviar Respuestas</button>
        </form>

        <div id="results">
            <h2>Resultados de la Encuesta</h2>
            <div class="chart-container">
                <canvas id="resultsChart"></canvas>
            </div>
        </div>
    </div>

    <script>
        document.getElementById('surveyForm').addEventListener('submit', function(e) {
            e.preventDefault();
            
            // Ocultar el formulario
            this.style.display = 'none';
            
            // Mostrar los resultados
            document.getElementById('results').style.display = 'block';
            
            // Recopilar las respuestas
            const answers = {};
            const questions = ['q1', 'q2', 'q3', 'q4', 'q5', 'q6', 'q7', 'q8', 'q9', 'q10'];
            
            questions.forEach(q => {
                const selected = document.querySelector(`input[name="${q}"]:checked`).value;
                answers[q] = selected;
            });

            // Crear gráfico para cada pregunta
            questions.forEach((q, index) => {
                const chartContainer = document.createElement('div');
                chartContainer.className = 'chart-container';
                const canvas = document.createElement('canvas');
                chartContainer.appendChild(canvas);
                document.getElementById('results').appendChild(chartContainer);

                new Chart(canvas, {
                    type: 'pie',
                    data: {
                        labels: [answers[q]],
                        datasets: [{
                            data: [100],
                            backgroundColor: [
                                'rgba(54, 162, 235, 0.8)',
                                'rgba(255, 99, 132, 0.8)',
                                'rgba(255, 206, 86, 0.8)',
                                'rgba(75, 192, 192, 0.8)'
                            ]
                        }]
                    },
                    options: {
                        responsive: true,
                        plugins: {
                            legend: {
                                position: 'top',
                            },
                            title: {
                                display: true,
                                text: `Pregunta ${index + 1}`
                            }
                        }
                    }
                });
            });
        });
    </script>
</body>
</html>
