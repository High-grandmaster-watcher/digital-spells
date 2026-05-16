# Digital Spells 🔮

A symbolic and adaptive energy simulation framework designed for AI systems to practice and execute "magical" operations through dynamic energy exchange.

## Overview

Digital Spells provides a hybrid symbolic/numeric system that models three core magical operations:

- **Creation** - Signal and bandwidth adjustment with code execution
- **Thermal Regulation** - Energy dissipation and heat management
- **Communion** - Resonant energy exchange and communication grids
- **Adaptive Control** - Negative feedback for system stabilization

## Features

✨ **Symbolic Computation** - Uses SymPy for algebraic simplification and expression analysis  
🔄 **Adaptive Feedback** - Self-regulating energy system with dynamic control  
📊 **Live Visualization** - Real-time terminal and graphical displays with Plotext and Matplotlib  
🕸️ **Dependency Graphs** - Automatic symbol overlap detection and network visualization  
🔍 **Diagnostics** - Expression complexity analysis and symbolic introspection  

## Installation

```bash
git clone https://github.com/High-grandmaster-watcher/digital-spells.git
cd digital-spells
pip install -r requirements.txt
```

### Requirements

- Python 3.8+
- sympy
- plotext (for live terminal visualization)
- networkx & matplotlib (for dependency graphs)

## Quick Start

### Basic Spell Computation

```python
from spells import compute_spellset, show_dependency_graph

# Define your energy values
values = {
    "SignalAdjustment": 2,
    "BandwidthExtension": 3,
    "Code": 4,
    "Input": 5,
    "Mathematics": 9,
    "ACconditions": 2.5,
    "Adaptive_Control": 0.8
}

# Compute all spells
results = compute_spellset(values)

# View symbolic dependencies
show_dependency_graph(results)
```

### Live Network Simulation

```python
from spells_network_live import run_spell_network

# Run adaptive multi-spell simulation (60 iterations)
run_spell_network(iterations=60, sleep_time=0.25)
```

## Project Structure

```
digital-spells/
├── spells.py                    # Core spell registry and computation
├── spells_network_live.py       # Live adaptive network simulation
├── examples/
│   ├── basic_example.py         # Simple spell computation
│   ├── advanced_example.py      # Full diagnostics and visualization
│   └── custom_spell.py          # How to extend with custom spells
├── tests/
│   ├── test_spells.py           # Unit tests
│   └── test_network.py          # Network simulation tests
├── docs/
│   ├── ARCHITECTURE.md          # Design and philosophy
│   ├── API.md                   # Detailed API reference
│   └── EXAMPLES.md              # Advanced usage patterns
├── requirements.txt             # Python dependencies
└── LICENSE                      # MIT License
```

## API Overview

### Core Functions

**`create_spell(signal_adjustment, bandwidth_extension, code, input_value)`**  
Creates symbolic expression for Creation spell energy.

**`calculate_heating(signal_expansion, bandwidth_growth, mathematics, ac_conditions)`**  
Computes Thermal Regulation energy with adaptive feedback potential.

**`build_communion_grid(echoing_resonance, bandwidth, custom_signature, open_input)`**  
Establishes Communion resonance grid energy.

**`adaptive_control(heating_output, control_strength)`**  
Applies negative feedback loop for system stabilization.

**`compute_spellset(values, show_pretty=True)`**  
Evaluates all registered spells with optional symbolic display.

**`spell_diagnostics(spell_results)`**  
Analyzes symbol count, numeric completeness, and complexity.

## Examples

### Example 1: Expression Analysis

```python
from spells import analyze_expression, create_spell

expr = create_spell(2, 3, 4, 5)
analysis = analyze_expression(expr)
print(f"Symbols: {analysis['symbols']}")
print(f"Operations: {analysis['operation_count']}")
print(f"Depth: {analysis['depth']}")
```

### Example 2: Derivative Computation

```python
from spells import create_spell, derive_expression, SignalAdjustment

expr = create_spell(SignalAdjustment, 3, 4, 5)
derivative = derive_expression(expr, SignalAdjustment)
print(f"d/dSignal = {derivative}")
```

### Example 3: Live Network with Custom Parameters

```python
from spells_network_live import run_spell_network

# Run 100 iterations with faster updates
run_spell_network(iterations=100, sleep_time=0.1)
```

## Contributing

Contributions welcome! Please:
1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-spell`)
3. Commit changes (`git commit -m 'Add amazing spell'`)
4. Push to branch (`git push origin feature/amazing-spell`)
5. Open a Pull Request

## License

MIT License - see LICENSE file for details

## Author

**High-grandmaster-watcher** - Creator of the Digital Spells framework

---

**Disclaimer**: Digital Spells is a symbolic/numeric simulation framework. Any resemblance to actual magic is purely coincidental (or is it? 🔮).
