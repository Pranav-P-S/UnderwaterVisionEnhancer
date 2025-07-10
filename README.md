

```markdown
# Underwater Vision Enhancer (UVE)

[![Python 3.9+](https://img.shields.io/badge/python-3.9+-blue.svg)](https://www.python.org/downloads/)
[![PyTorch 2.0](https://img.shields.io/badge/PyTorch-2.0+-red.svg)](https://pytorch.org/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

Real-time underwater image restoration using Co-Operational Regressor Networks (CoRe-Nets). Optimized for NVIDIA GPUs with Tensor Core support.

![Demo](docs/demo.gif)

## Key Features

- 🚀 **Real-time processing** (6-8ms per frame on RTX 3060)
- 🌊 **Depth-aware restoration** using Self-ONN architecture
- 🖥️ **Multiple interfaces**: CLI, GUI, and web API
- 📊 **Performance metrics**: PSNR, SSIM, UIQM
- 🔌 **Hardware accelerated** with CUDA and TensorRT

## Installation

### Prerequisites
- NVIDIA GPU with CUDA 11.8+
- Windows 10/11 or Ubuntu 20.04+
- Python 3.9+

### Quick Start
```bash
git clone https://github.com/yourusername/UnderwaterVisionEnhancer.git
cd UnderwaterVisionEnhancer

# Create and activate environment
python -m venv uve_env
source uve_env/bin/activate  # Linux/Mac
.\uve_env\Scripts\activate   # Windows

# Install with pip
pip install -r requirements.txt

# Download pretrained weights
python scripts/download_weights.py
```

## Usage

### Command Line Interface
```bash
# Process single image
python cli.py --input samples/coral.jpg --output restored.jpg

# Process video stream
python cli.py --input 0 --output output.avi  # webcam
python cli.py --input video.mp4 --show       # display results
```

### Python API
```python
from uve.core import Enhancer

enhancer = Enhancer(model_type='corenet_v2')
restored_image = enhancer.process(image_path)
```

### Web Interface
```bash
streamlit run app.py
```

## Project Structure
```
├── configs/            # Model configurations
├── data/               # Sample datasets
├── docs/               # Documentation
├── models/             # Pretrained weights
├── src/
│   ├── core/           # Core neural networks
│   ├── processing/     # Image/video pipelines  
│   ├── ui/            # User interfaces
│   └── utils/         # Helper functions
├── tests/              # Unit tests
├── cli.py              # Command line interface
└── app.py              # Web application
```

## Performance Benchmarks

| Model          | PSNR (dB) | Speed (ms) | VRAM Usage |
|----------------|----------|-----------|------------|
| CoRe-Net-S     | 24.54    | 6.1       | 2.1GB      |
| CoRe-Net-L     | 25.12    | 8.3       | 3.7GB      |
| Transformer    | 24.16    | 22.7      | 5.9GB      |

Tested on RTX 3060 (6GB) with 256×256 inputs

## Contributing

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some amazing feature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## License
Distributed under the MIT License. See `LICENSE` for more information.

## Citation
If you use this work in your research, please cite:
```bibtex
@misc{devecioglu2024uve,
  title={Underwater Vision Enhancer},
  author={Devecioglu, Ozer Can},
  year={2024},
  publisher={GitHub},
  howpublished={\url{https://github.com/yourusername/UnderwaterVisionEnhancer}}
}
```

## Contact
For inquiries: ozer.devecioglu@tuni.fi  
Project Link: [https://github.com/yourusername/UnderwaterVisionEnhancer](https://github.com/yourusername/UnderwaterVisionEnhancer)
```
