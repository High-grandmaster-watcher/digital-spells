# API Reference

## Core Spell Functions

### `create_spell(signal_adjustment, bandwidth_extension, code, input_value)`

Computes Creation spell energy through signal and bandwidth modulation.

**Returns**: Simplified SymPy expression  
**Expression**: `signal_adjustment + bandwidth_extension + (code * input_value)`

```python
from spells import create_spell, SignalAdjustment
expr = create_spell(SignalAdjustment, 3, 4, 5)
```

### `calculate_heating(signal_expansion, bandwidth_growth, mathematics, ac_conditions)`

Computes Thermal Regulation energy dissipation.

**Returns**: Simplified SymPy expression  
**Expression**: `signal_expansion + bandwidth_growth + (mathematics * ac_conditions)`

```python
from spells import calculate_heating, SignalExpansion
expr = calculate_heating(SignalExpansion, 2, 3.3, 1.5)
```

### `build_communion_grid(echoing_resonance, bandwidth, custom_signature, open_input)`

Constructs Communion resonance grid for energy exchange.

**Returns**: Expanded SymPy expression  
**Expression**: `echoing_resonance + bandwidth + (custom_signature * open_input)`

```python
from spells import build_communion_grid, EchoingResonance
expr = build_communion_grid(EchoingResonance, 2.2, 1.1, 2)
```

### `adaptive_control(heating_output, control_strength)`

Applies negative feedback for system stabilization.

**Returns**: Simplified SymPy expression  
**Expression**: `-control_strength * heating_output`

```python
from spells import adaptive_control
control = adaptive_control(total_energy, 0.85)
```

## Computation & Analysis

### `compute_spellset(values=None, show_pretty=True)`

Evaluates all registered spells with optional terminal display.

**Parameters**:
- `values` (dict): Substitution mapping {symbol_name: numeric_value}
- `show_pretty` (bool): Print results with SymPy pretty-printing

**Returns**: Dictionary mapping spell names to computed expressions

```python
values = {
    "SignalAdjustment": 2,
    "BandwidthExtension": 3,
    "Code": 4,
    "Input": 5,
}
results = compute_spellset(values, show_pretty=True)
```

### `spell_diagnostics(spell_results)`

Analyzes symbolic complexity and numeric completeness.

**Parameters**:
- `spell_results` (dict): Output from `compute_spellset()`

**Returns**: Dictionary with diagnostics per spell:
```python
{
    "spell_name": {
        "symbol_count": int,
        "is_fully_numeric": bool,
        "complexity": int
    },
    ...
}
```

### `analyze_expression(expr)`

Structural metrics for a single symbolic expression.

**Parameters**:
- `expr` (SymPy Expr): Symbolic expression to analyze

**Returns**: Dictionary with:
- `symbols` (list): Symbols present in expression
- `symbol_count` (int): Number of unique symbols
- `operation_count` (int): Count of Add/Mul/Pow operations
- `depth` (int): Max nesting depth of expression tree

```python
from spells import create_spell, analyze_expression, SignalAdjustment
expr = create_spell(SignalAdjustment, 3, 4, 5)
metrics = analyze_expression(expr)
print(f"Complexity: {metrics['operation_count']}")
```

### `derive_expression(expr, var)`

Computes symbolic derivative of expression with respect to variable.

**Parameters**:
- `expr` (SymPy Expr): Expression to differentiate
- `var` (SymPy Symbol): Variable to differentiate by

**Returns**: Simplified SymPy derivative expression

```python
from spells import create_spell, derive_expression, SignalAdjustment, Code
expr = create_spell(SignalAdjustment, 3, Code, 5)
d_dx = derive_expression(expr, SignalAdjustment)
d_dcode = derive_expression(expr, Code)
```

## Dependency & Visualization

### `compute_symbol_overlap(spell_results)`

Computes symbolic dependencies between spells.

**Parameters**:
- `spell_results` (dict): Output from `compute_spellset()`

**Returns**: List of tuples: `[(spell_a, spell_b, shared_symbols), ...]`

```python
overlaps = compute_symbol_overlap(results)
for a, b, shared in overlaps:
    print(f"{a} uses same symbols as {b}: {shared}")
```

### `show_dependency_graph(spell_results)`

Prints text-based dependency relationships.

**Parameters**:
- `spell_results` (dict): Output from `compute_spellset()`

**Output**: Terminal display of symbol sharing

```python
show_dependency_graph(results)
```

### `visualize_dependency_graph(spell_results)`

Renders NetworkX graph visualization (requires matplotlib).

**Parameters**:
- `spell_results` (dict): Output from `compute_spellset()`

**Requirements**: `networkx` and `matplotlib` packages

```python
visualize_dependency_graph(results)
```

## Live Simulation

### `run_spell_network(iterations=60, sleep_time=0.25)`

Executes adaptive multi-spell energy simulation with live terminal visualization.

**Parameters**:
- `iterations` (int): Number of simulation cycles
- `sleep_time` (float): Delay between frames (seconds)

**Displays**:
- Real-time ASCII plot with Plotext
- Console status updates per cycle
- Final stabilization score

**Requirements**: `plotext` package

```python
from spells_network_live import run_spell_network

# Run 100 iterations with 0.1s per frame
run_spell_network(iterations=100, sleep_time=0.1)
```

## Symbols Registry

Global symbolic variables available for use:

```python
from spells import (
    SignalAdjustment, BandwidthExtension, Code, Input,
    SignalExpansion, BandwidthGrowth, Mathematics, ACconditions,
    EchoingResonance, Bandwidth, CustomSignature, OpenInput,
    AdaptiveControlSym
)
```

Use these to build custom spell expressions:

```python
from spells import SignalAdjustment, Code
my_expr = SignalAdjustment**2 + Code
```

## Error Handling

All functions use SymPy's exception types. Common scenarios:

```python
from sympy import SympifyError

try:
    results = compute_spellset(invalid_values)
except (TypeError, ValueError) as e:
    print(f"Invalid spell computation: {e}")
```

## Performance Notes

- SymPy simplification can be expensive for large expressions
- Float conversion in simulations may lose symbolic precision
- Visualization layout computation scales with spell count
- Keep symbol counts < 50 for responsive analysis
