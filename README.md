   <style>
        :root {
            --brand-color: #6A50EF;
            --brand-hover: #5840d9;
            --brand-active: #4935c3;
            --text-color: #000000;
            --bg-color: #ffffff;
            --border-color: #dee2e6;
            --result-bg: #f8f9fa;
            --result-success: #e8f0fe;
        }

        body {
            background-color: var(--bg-color);
            color: var(--text-color);
        }

        .calc-container {
            max-width: 800px;
            margin: 2rem auto;
        }

        .calculator-section {
            background-color: var(--bg-color);
            border: 1px solid var(--border-color);
            border-radius: 10px;
            padding: 1.5rem;
            margin-bottom: 1.5rem;
            box-shadow: 0 2px 4px rgba(0, 0, 0, 0.05);
        }

        .result {
            transition: background-color 0.3s;
            min-height: 60px;
            white-space: pre-line;
            background-color: var(--result-bg);
            border: 1px solid var(--border-color);
            padding: 10px;
            border-radius: 5px;
        }

        .form-control:focus {
            border-color: var(--brand-color);
            box-shadow: 0 0 0 0.25rem rgba(106, 80, 239, 0.25);
        }

        .nav-pills .nav-link {
            color: var(--text-color);
            margin: 0 0.25rem;
        }

        .nav-pills .nav-link:hover {
            background-color: rgba(106, 80, 239, 0.1);
        }

        .nav-pills .nav-link.active {
            background-color: var(--brand-color);
            color: var(--bg-color);
        }

        .btn-primary {
            background-color: var(--brand-color);
            border-color: var(--brand-color);
            color: white;
        }

        .btn-primary:hover {
            background-color: var(--brand-hover);
            border-color: var(--brand-hover);
        }

        .btn-primary:active {
            background-color: var(--brand-active) !important;
            border-color: var(--brand-active) !important;
        }

        .history-item {
            font-size: 0.9rem;
            padding: 0.5rem;
            border-bottom: 1px solid var(--border-color);
            color: var(--text-color);
        }

        .bg-success-subtle {
            background-color: var(--result-success) !important;
        }

        .input-group-text {
            background-color: var(--result-bg);
            border-color: var(--border-color);
            color: var(--text-color);
        }

        .form-check-input:checked {
            background-color: var(--brand-color);
            border-color: var(--brand-color);
        }

        .form-select:focus {
            border-color: var(--brand-color);
            box-shadow: 0 0 0 0.25rem rgba(106, 80, 239, 0.25);
        }
    </style>

    <div class="container calc-container">
        <h1 class="text-center mb-4">
            <i class="bi bi-calculator"></i> Percentage Calculator
        </h1>

        <!-- Navigation -->
        <ul class="nav nav-pills mb-4 justify-content-center flex-wrap" id="calculatorTabs" role="tablist">
            <li class="nav-item" role="presentation">
                <button class="nav-link active" data-bs-toggle="pill" data-bs-target="#basicCalc">Basic</button>
            </li>
            <li class="nav-item" role="presentation">
                <button class="nav-link" data-bs-toggle="pill" data-bs-target="#differenceCalc">Difference</button>
            </li>
            <li class="nav-item" role="presentation">
                <button class="nav-link" data-bs-toggle="pill" data-bs-target="#fractionCalc">Fraction ↔ %</button>
            </li>
            <li class="nav-item" role="presentation">
                <button class="nav-link" data-bs-toggle="pill" data-bs-target="#reverseCalc">Reverse</button>
            </li>
            <li class="nav-item" role="presentation">
                <button class="nav-link" data-bs-toggle="pill" data-bs-target="#relativeCalc">Relative %</button>
            </li>
            <li class="nav-item" role="presentation">
                <button class="nav-link" data-bs-toggle="pill" data-bs-target="#markupCalc">Markup</button>
            </li>
            <li class="nav-item" role="presentation">
                <button class="nav-link" data-bs-toggle="pill" data-bs-target="#tipCalc">Tip</button>
            </li>
            <li class="nav-item" role="presentation">
                <button class="nav-link" data-bs-toggle="pill" data-bs-target="#distributionCalc">Distribution</button>
            </li>
        </ul>

        <div class="tab-content">
            <!-- Basic Percentage Calculator -->
            <div class="tab-pane fade show active" id="basicCalc">
                <div class="calculator-section">
                    <h3>Calculate Percentage of a Number</h3>
                    <div class="row g-3 align-items-center mb-3">
                        <div class="col-md-4">
                            <div class="input-group">
                                <input type="number" class="form-control" id="percentValue" placeholder="Enter percentage">
                                <span class="input-group-text">%</span>
                            </div>
                        </div>
                        <div class="col-md-4">
                            <div class="input-group">
                                <span class="input-group-text">of</span>
                                <input type="number" class="form-control" id="baseValue" placeholder="Enter number">
                            </div>
                        </div>
                        <div class="col-md-4">
                            <div class="result" id="basicResult">
                                Result will appear here
                            </div>
                        </div>
                    </div>
                </div>
            </div>

            <!-- Percentage Difference Calculator -->
            <div class="tab-pane fade" id="differenceCalc">
                <div class="calculator-section">
                    <h3>Calculate Percentage Change</h3>
                    <div class="row g-3 align-items-center mb-3">
                        <div class="col-md-4">
                            <input type="number" class="form-control" id="oldValue" placeholder="Original value">
                        </div>
                        <div class="col-md-4">
                            <input type="number" class="form-control" id="newValue" placeholder="New value">
                        </div>
                        <div class="col-md-4">
                            <div class="result" id="differenceResult">
                                Result will appear here
                            </div>
                        </div>
                    </div>
                </div>
            </div>

            <!-- Fraction to Percentage Calculator -->
            <div class="tab-pane fade" id="fractionCalc">
                <div class="calculator-section">
                    <h3>Fraction ↔ Percentage Converter</h3>
                    <div class="row g-3 mb-3">
                        <div class="col-md-6">
                            <h5>Fraction to Percentage</h5>
                            <div class="input-group mb-2">
                                <input type="number" class="form-control" id="numerator" placeholder="Numerator">
                                <span class="input-group-text">/</span>
                                <input type="number" class="form-control" id="denominator" placeholder="Denominator">
                            </div>
                            <div class="result" id="fractionToPercentResult">
                                Result will appear here
                            </div>
                        </div>
                        <div class="col-md-6">
                            <h5>Percentage to Fraction</h5>
                            <div class="input-group mb-2">
                                <input type="number" class="form-control" id="percentageToFraction" placeholder="Enter percentage">
                                <span class="input-group-text">%</span>
                            </div>
                            <div class="result" id="percentToFractionResult">
                                Result will appear here
                            </div>
                        </div>
                    </div>
                </div>
            </div>

            <!-- Placeholder for other calculator sections -->
            <div class="tab-pane fade" id="reverseCalc">
                <div class="calculator-section">
                    <h3>Reverse Percentage Calculator</h3>
                    <div class="row g-3 align-items-center mb-3">
                        <div class="col-md-4">
                            <div class="input-group">
                                <input type="number" class="form-control" id="resultValue" placeholder="Result value">
                            </div>
                        </div>
                        <div class="col-md-4">
                            <div class="input-group">
                                <span class="input-group-text">is</span>
                                <input type="number" class="form-control" id="percentValueReverse" placeholder="Percentage">
                                <span class="input-group-text">%</span>
                            </div>
                        </div>
                        <div class="col-md-4">
                            <div class="result" id="reverseResult">Result will appear here</div>
                        </div>
                    </div>
                </div>
            </div>
            <div class="tab-pane fade" id="relativeCalc">
                <div class="calculator-section">
                    <h3>Relative Percentage Calculator</h3>
                    <div class="row g-3 align-items-center mb-3">
                        <div class="col-md-4">
                            <div class="input-group">
                                <input type="number" class="form-control" id="valueA" placeholder="Value A">
                            </div>
                        </div>
                        <div class="col-md-4">
                            <div class="input-group">
                                <span class="input-group-text">is what percent of</span>
                                <input type="number" class="form-control" id="valueB" placeholder="Value B">
                            </div>
                        </div>
                        <div class="col-md-4">
                            <div class="result" id="relativeResult">Result will appear here</div>
                        </div>
                    </div>
                </div>
            </div>
            <div class="tab-pane fade" id="markupCalc">
                <div class="calculator-section">
                    <h3>Markup Calculator</h3>
                    <div class="row g-3 align-items-center mb-3">
                        <div class="col-md-4">
                            <div class="input-group">
                                <input type="number" class="form-control" id="costValue" placeholder="Cost">
                            </div>
                        </div>
                        <div class="col-md-4">
                            <div class="input-group">
                                <span class="input-group-text">markup by</span>
                                <input type="number" class="form-control" id="markupPercent" placeholder="Markup Percentage">
                                <span class="input-group-text">%</span>
                            </div>
                        </div>
                        <div class="col-md-4">
                            <div class="result" id="markupResult">Result will appear here</div>
                        </div>
                    </div>
                </div>
            </div>
            <div class="tab-pane fade" id="tipCalc">
                <div class="calculator-section">
                    <h3>Tip Calculator</h3>
                    <div class="row g-3 align-items-center mb-3">
                        <div class="col-md-4">
                            <div class="input-group">
                                <input type="number" class="form-control" id="billValue" placeholder="Bill Amount">
                            </div>
                        </div>
                        <div class="col-md-4">
                            <div class="input-group">
                                <span class="input-group-text">tip by</span>
                                <input type="number" class="form-control" id="tipPercent" placeholder="Tip Percentage">
                                <span class="input-group-text">%</span>
                            </div>
                        </div>
                        <div class="col-md-4">
                            <div class="result" id="tipResult">Result will appear here</div>
                        </div>
                    </div>
                </div>
            </div>
            <div class="tab-pane fade" id="distributionCalc">
                <div class="calculator-section">
                    <h3>Distribution Calculator</h3>
                    <div class="row g-3 mb-3">
                        <div class="col-md-6">
                            <input type="number" class="form-control" id="totalValueDistribution" placeholder="Total Value">
                        </div>
                        <div class="col-md-6">
                            <input type="number" class="form-control" id="numPartsDistribution" placeholder="Number of Parts">
                        </div>
                    </div>
                    <div class="result" id="distributionResult">Result will appear here</div>
                </div>
            </div>

        </div>

        <!-- Calculation History -->
        <div class="calculator-section mt-4">
            <h3>Recent Calculations</h3>
            <div id="calculationHistory" class="mt-3">
                <!-- History items will be added here dynamically -->
            </div>
        </div>

        <!-- Reset Button -->
        <div class="text-center mt-4">
            <button class="btn btn-primary" onclick="resetCalculator()">
                <i class="bi bi-arrow-counterclockwise"></i> Reset All
            </button>
        </div>
    </div>

    <!-- Bootstrap JS -->
    <script src="https://cdn.jsdelivr.net/npm/bootstrap@5.3.0/dist/js/bootstrap.bundle.min.js"></script>
    <script>
        // Initialize tooltips
        document.addEventListener('DOMContentLoaded', function() {
            var tooltipTriggerList = [].slice.call(document.querySelectorAll('[data-bs-toggle="tooltip"]'))
            var tooltipList = tooltipTriggerList.map(function(tooltipTriggerEl) {
                return new bootstrap.Tooltip(tooltipTriggerEl)
            });
        });

        // Basic Percentage Calculator
        const percentValue = document.getElementById('percentValue');
        const baseValue = document.getElementById('baseValue');
        const basicResult = document.getElementById('basicResult');

        [percentValue, baseValue].forEach(input => {
            input.addEventListener('input', calculateBasicPercentage);
        });

        function calculateBasicPercentage() {
            try {
                const percent = parseFloat(percentValue.value);
                const base = parseFloat(baseValue.value);

                if (isNaN(percent) || isNaN(base)) {
                    basicResult.textContent = 'Please enter valid numbers';
                    return;
                }

                const result = (percent / 100) * base;
                const text = `${percent}% of ${base} = ${result.toFixed(2)}`;
                basicResult.textContent = text;
                addToHistory(text);
                basicResult.classList.add('bg-success-subtle');
                setTimeout(() => basicResult.classList.remove('bg-success-subtle'), 300);
            } catch (error) {
                basicResult.textContent = 'Error in calculation';
            }
        }

        // Difference Calculator
        const oldValue = document.getElementById('oldValue');
        const newValue = document.getElementById('newValue');
        const differenceResult = document.getElementById('differenceResult');

        [oldValue, newValue].forEach(input => {
            input.addEventListener('input', calculatePercentageDifference);
        });

        function calculatePercentageDifference() {
            try {
                const original = parseFloat(oldValue.value);
                const current = parseFloat(newValue.value);

                if (isNaN(original) || isNaN(current)) {
                    differenceResult.textContent = 'Please enter valid numbers';
                    return;
                }

                if (original === 0) {
                    differenceResult.textContent = 'Original value cannot be zero';
                    return;
                }

                const difference = ((current - original) / Math.abs(original)) * 100;
                const type = difference >= 0 ? 'increase' : 'decrease';
                const text = `${Math.abs(difference).toFixed(2)}% ${type}`;
                differenceResult.textContent = text;
                addToHistory(`From ${original} to ${current}: ${text}`);
                differenceResult.classList.add('bg-success-subtle');
                setTimeout(() => differenceResult.classList.remove('bg-success-subtle'), 300);
            } catch (error) {
                differenceResult.textContent = 'Error in calculation';
            }
        }

        // Fraction Calculator
        const numerator = document.getElementById('numerator');
        const denominator = document.getElementById('denominator');
        const fractionToPercentResult = document.getElementById('fractionToPercentResult');
        const percentageToFraction = document.getElementById('percentageToFraction');
        const percentToFractionResult = document.getElementById('percentToFractionResult');

        function gcd(a, b) {
            return b === 0 ? a : gcd(b, a % b);
        }

        function simplifyFraction(num, den) {
            const divisor = gcd(Math.abs(num), Math.abs(den));
            return [num / divisor, den / divisor];
        }

        [numerator, denominator].forEach(input => {
            input.addEventListener('input', calculateFractionToPercent);
        });

        percentageToFraction.addEventListener('input', calculatePercentToFraction);

        function calculateFractionToPercent() {
            try {
                const num = parseFloat(numerator.value);
                const den = parseFloat(denominator.value);

                if (isNaN(num) || isNaN(den)) {
                    fractionToPercentResult.textContent = 'Please enter valid numbers';
                    return;
                }

                if (den === 0) {
                    fractionToPercentResult.textContent = 'Denominator cannot be zero';
                    return;
                }

                const percentage = (num / den) * 100;
                const text = `${num}/${den} = ${percentage.toFixed(2)}%`;
                fractionToPercentResult.textContent = text;
                addToHistory(text);
                fractionToPercentResult.classList.add('bg-success-subtle');
                setTimeout(() => fractionToPercentResult.classList.remove('bg-success-subtle'), 300);
            } catch (error) {
                fractionToPercentResult.textContent = 'Error in calculation';
            }
        }

        function calculatePercentToFraction() {
            try {
                const percent = parseFloat(percentageToFraction.value);

                if (isNaN(percent)) {
                    percentToFractionResult.textContent = 'Please enter a valid number';
                    return;
                }

                const decimal = percent / 100;
                const [num, den] = simplifyFraction(decimal * 1000, 1000);
                const text = `${percent}% = ${num}/${den}\nDecimal: ${decimal.toFixed(3)}`;
                percentToFractionResult.textContent = text;
                addToHistory(`${percent}% as fraction: ${num}/${den}`);
                percentToFractionResult.classList.add('bg-success-subtle');
                setTimeout(() => percentToFractionResult.classList.remove('bg-success-subtle'), 300);
            } catch (error) {
                percentToFractionResult.textContent = 'Error in calculation';
            }
        }

        // Reverse Percentage Calculator
        const resultValue = document.getElementById('resultValue');
        const percentValueReverse = document.getElementById('percentValueReverse');
        const reverseResult = document.getElementById('reverseResult');

        [resultValue, percentValueReverse].forEach(input => {
            input.addEventListener('input', calculateReversePercentage);
        });

        function calculateReversePercentage() {
            try {
                const result = parseFloat(resultValue.value);
                const percent = parseFloat(percentValueReverse.value);

                if (isNaN(result) || isNaN(percent)) {
                    reverseResult.textContent = 'Please enter valid numbers';
                    return;
                }

                if (percent === 0) {
                    reverseResult.textContent = 'Percentage cannot be zero';
                    return;
                }

                const base = (result / (percent / 100));
                const text = `${result} is ${percent}% of ${base.toFixed(2)}`;
                reverseResult.textContent = text;
                addToHistory(text);
                reverseResult.classList.add('bg-success-subtle');
                setTimeout(() => reverseResult.classList.remove('bg-success-subtle'), 300);
            } catch (error) {
                reverseResult.textContent = 'Error in calculation';
            }
        }


        // Relative Percentage Calculator
        const valueA = document.getElementById('valueA');
        const valueB = document.getElementById('valueB');
        const relativeResult = document.getElementById('relativeResult');

        [valueA, valueB].forEach(input => {
            input.addEventListener('input', calculateRelativePercentage);
        });

        function calculateRelativePercentage() {
            try {
                const a = parseFloat(valueA.value);
                const b = parseFloat(valueB.value);

                if (isNaN(a) || isNaN(b)) {
                    relativeResult.textContent = 'Please enter valid numbers';
                    return;
                }

                if (b === 0) {
                    relativeResult.textContent = 'Value B cannot be zero';
                    return;
                }

                const percentage = (a / b) * 100;
                const text = `${a} is ${percentage.toFixed(2)}% of ${b}`;
                relativeResult.textContent = text;
                addToHistory(text);
                relativeResult.classList.add('bg-success-subtle');
                setTimeout(() => relativeResult.classList.remove('bg-success-subtle'), 300);
            } catch (error) {
                relativeResult.textContent = 'Error in calculation';
            }
        }

        // Markup Calculator
        const costValue = document.getElementById('costValue');
        const markupPercent = document.getElementById('markupPercent');
        const markupResult = document.getElementById('markupResult');

        [costValue, markupPercent].forEach(input => {
            input.addEventListener('input', calculateMarkup);
        });

        function calculateMarkup() {
            try {
                const cost = parseFloat(costValue.value);
                const markup = parseFloat(markupPercent.value);

                if (isNaN(cost) || isNaN(markup)) {
                    markupResult.textContent = 'Please enter valid numbers';
                    return;
                }

                const finalPrice = cost * (1 + markup / 100);
                const text = `Markup: ${markup}%, Cost: ${cost}, Final Price: ${finalPrice.toFixed(2)}`;
                markupResult.textContent = text;
                addToHistory(text);
                markupResult.classList.add('bg-success-subtle');
                setTimeout(() => markupResult.classList.remove('bg-success-subtle'), 300);
            } catch (error) {
                markupResult.textContent = 'Error in calculation';
            }
        }


        // Tip Calculator
        const billValue = document.getElementById('billValue');
        const tipPercent = document.getElementById('tipPercent');
        const tipResult = document.getElementById('tipResult');

        [billValue, tipPercent].forEach(input => {
            input.addEventListener('input', calculateTip);
        });

        function calculateTip() {
            try {
                const bill = parseFloat(billValue.value);
                const tip = parseFloat(tipPercent.value);

                if (isNaN(bill) || isNaN(tip)) {
                    tipResult.textContent = 'Please enter valid numbers';
                    return;
                }

                const tipAmount = bill * (tip / 100);
                const total = bill + tipAmount;
                const text = `Bill: ${bill}, Tip (%${tip}): ${tipAmount.toFixed(2)}, Total: ${total.toFixed(2)}`;
                tipResult.textContent = text;
                addToHistory(text);
                tipResult.classList.add('bg-success-subtle');
                setTimeout(() => tipResult.classList.remove('bg-success-subtle'), 300);
            } catch (error) {
                tipResult.textContent = 'Error in calculation';
            }
        }

        // Distribution Calculator
        const totalValueDistribution = document.getElementById('totalValueDistribution');
        const numPartsDistribution = document.getElementById('numPartsDistribution');
        const distributionResult = document.getElementById('distributionResult');

        [totalValueDistribution, numPartsDistribution].forEach(input => {
            input.addEventListener('input', calculateDistribution);
        });

        function calculateDistribution() {
            try {
                const total = parseFloat(totalValueDistribution.value);
                const numParts = parseFloat(numPartsDistribution.value);

                if (isNaN(total) || isNaN(numParts)) {
                    distributionResult.textContent = 'Please enter valid numbers';
                    return;
                }

                if (numParts <= 0) {
                    distributionResult.textContent = 'Number of parts must be greater than zero';
                    return;
                }

                const perPart = total / numParts;
                const text = `Total: ${total}, Parts: ${numParts}, Per Part: ${perPart.toFixed(2)}`;
                distributionResult.textContent = text;
                addToHistory(text);
                distributionResult.classList.add('bg-success-subtle');
                setTimeout(() => distributionResult.classList.remove('bg-success-subtle'), 300);
            } catch (error) {
                distributionResult.textContent = 'Error in calculation';
            }
        }


        // History Management
        const maxHistoryItems = 5;
        const calculationHistory = document.getElementById('calculationHistory');

        function addToHistory(calculation) {
            const historyItem = document.createElement('div');
            historyItem.className = 'history-item';
            historyItem.textContent = calculation;

            if (calculationHistory.children.length >= maxHistoryItems) {
                calculationHistory.removeChild(calculationHistory.lastChild);
            }

            calculationHistory.insertBefore(historyItem, calculationHistory.firstChild);
        }

        // Reset Calculator
        function resetCalculator() {
            document.querySelectorAll('input').forEach(input => {
                input.value = '';
            });
            document.querySelectorAll('.result').forEach(result => {
                result.textContent = 'Result will appear here';
                result.classList.remove('bg-success-subtle');
            });
            calculationHistory.innerHTML = '';
        }
    </script>
