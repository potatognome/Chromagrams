Purpose
Chromagrams is the temporal animation engine for Chromaspace.
It consumes Chromaschemes outputs and produces:
- Keyframed sequences
- Interpolated frames
- Temporal geometric transforms
Chromagrams must register all animation sequences with the Chromacore Registry.

Project Structure
Chromagrams/
    src/chromagrams/
        sequences/
        interpolation/
        transforms/
        loaders/
        integration/
    config/
        CHROMAGRAMS_CONFIG.json
        CHROMAGRAMS.d/
    docs/
    tests/


Registry Integration
Copilot must ensure:
- All animation sequences use @register_animation
- Metadata is complete
- Capabilities are explicit (e.g., ["looping", "easing"])
Example:
@register_animation(
    name="pulse",
    version="1.0",
    capabilities=["looping", "amplitude"],
    config_schema="schemas/pulse.yaml",
)
class PulseSequence(AnimationInterface):
    ...


tUilKit Integration
Copilot must:
- Load config via tUilKit
- Support .d overrides
- Log animation execution
- Produce deterministic frame sequences

Interpolation + Transforms
Copilot must maintain:
- Interpolation curves (linear, bezier, easing)
- Temporal transforms (rotate, shift, distort)
All must be modular and registry‑discoverable.

Testing
Copilot must scaffold:
- Sequence tests
- Interpolation tests
- Config loading tests
- Deterministic frame tests
