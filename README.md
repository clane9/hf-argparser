# Huggingface argument parser

A standalone copy of the Huggingface argument parser copied verbatim from [🤗 transformers](https://github.com/huggingface/transformers/blob/main/src/transformers/hf_argparser.py).

## Example

```python
from dataclasses import dataclass
from pathlib import Path

from hf_argparser import HfArg, HfArgumentParser

@dataclass
class Args:
    input: Path = HfArg(aliases=["-i"], help="input path")
    output: Path = HfArg(aliases=["-o"], help="output path")

def main(args: Args):
    print(args)

if __name__ == "__main__":
    args: Args
    parser = HfArgumentParser(Args)
    (args,) = parser.parse_args_into_dataclasses()
    main(args)
```

## Installation

```sh
pip install git+https://github.com/clane9/hf-argparser.git
```
