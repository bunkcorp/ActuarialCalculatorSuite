
# Actuarial Calculator Suite

## Overview
The Actuarial Calculator Suite is a Python implementation of a Select and Ultimate Survival Model (SUSM) for actuarial calculations. It replicates and extends the functionality of actuarial Excel workbooks, enabling automated and reproducible computations for survival probabilities, annuities, insurance values, and more.

This tool is designed for actuaries, students, and professionals in the insurance and financial sectors who need precise and efficient actuarial modeling.

---

## Features
The calculator supports the following computations:

- **Mortality Metrics**:
  - \( q_x \): Mortality rate.
  - \( p_x \): Survival probability.
  - \( l_x \): Number of lives at age \( x \).

- **Annuity Values**:
  - \( ä_x \): Present value of a whole life annuity-due.
  - \( ä_x^{(m)} \): Monthly annuity-due.
  - \( ä_{x:n} \): Term annuities for \( n \)-years.

- **Insurance Values**:
  - \( A_x \): Present value of whole life insurance.
  - Term insurance and monthly insurance values.

- **Deferred Benefits**:
  - \( nE_x \): Pure endowment for various terms.

- **Interest Function Analysis**:
  - Effective interest and discount rates for various compounding frequencies.

---

## Installation

### Prerequisites
- Python 3.8 or higher
- Libraries: `numpy`, `pandas`

### Steps
1. Clone the repository:
   ```bash
   git clone https://github.com/bunkcorp/actuarial-calculator-suite.git
   cd actuarial-calculator-suite
   ```

2. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```

---

## Usage

### Example: Calculating Annuity and Insurance Values
```python
from actuarial_calculator import ActuarialCalculator, ActuarialParams

# Initialize parameters
params = ActuarialParams(
    i=0.05,  # Interest rate
    m=12,    # Payment frequency
    sel=0.9, # Selection factor
    A=0.00022,
    B=0.0000027,
    c=1.124
)

# Create a calculator instance
calc = ActuarialCalculator(params)

# Calculate values for ages 20 to 30
results = calc.calculate_all(start_age=20, end_age=30)

# Display results
print(results)
```

### Run the Script Directly
Run the `main()` function to calculate and display values for ages 20 to 130:
```bash
python actuarial_calculator.py
```
Results will be displayed in the console and saved as a CSV file (`results.csv`).

---

## Outputs
Sample outputs include:
| Age (\( x \)) | \( q_x \)   | \( p_x \)   | \( l_x \)   | \( ä_x \)   | \( A_x \)   | \( ä_{x:10} \) | \( ä_{x:20} \) |
|---------------|-------------|-------------|-------------|-------------|-------------|----------------|----------------|
| 20            | 0.00025     | 0.99975     | 100,000     | 19.966394   | 0.049219    | 8.099144       | 13.055894      |

The results align with actuarial Excel workbooks, including sheets for "Select and Ultimate Mortality," "Single Life Annuities," and "Interest Functions."

---

## Comparison with Excel
This implementation is based on the actuarial Excel workbook structure:
- **Select and Ultimate Mortality**: Parameters like \( A, B, c, 	ext{sel} \).
- **Single Life**: Annuity and insurance calculations (\( ä_x, A_x, nE_x \)).
- **Interest Functions**: Effective rates (\( i(m), d(m) \)).

---

## Advantages
- **Automation**: Eliminates manual operations in Excel.
- **Scalability**: Efficiently processes large datasets and extended age ranges.
- **Reproducibility**: Ensures consistent results across iterations.
- **Customizability**: Easily adjust parameters or extend functionalities.

---

## Contributions
Contributions are welcome! To contribute:
1. Fork the repository.
2. Create a new branch (`feature/your-feature`).
3. Commit your changes and submit a pull request.

---

## License
This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

---

## Acknowledgments
This project draws inspiration from actuarial Excel workbooks and aims to enhance actuarial calculations through Python automation.
