# RapidLLaMA: A High-Performance LLM Inference Engine

RapidLLaMA is a super `HIGH`-performance inference engine for LLMs like LLaMA (**3x** of `llama.cpp`) written in C++ which can run a 8-bit quantized `LLaMA2-7B` model on a cpu with 56 cores in speed of `~30 tokens / s`. It outperforms all current open-source inference engines, especially when compared to the renowned llama.cpp, with 2~3 times better inference speed on a CPU.

## Compilation

You can compile the code using one of the following two methods:

1. Using the provided build script:
```bash
bash ./build.sh
```

2. Using Make:
```bash
make -j 4
```

## Usage

To run the inference engine, execute the following command:

```bash
./main -c ./models/cnllama-7b/ggml-model-f32.gguf -f gguf -j 56 -q int8 -n 200 -i 'That was a long long story happened in the ancient China.'
```

The command-line options are as follows:

- `-c`: Path to the model file
- `-f`: Model file format (e.g., gguf)
- `-j`: Number of threads to use (e.g., 56)
- `-q`: Quantization mode (e.g., int8)
- `-n`: Number of tokens to generate (e.g., 200)
- `-i`: Input text (e.g., 'That was a long long story happened in the ancient China.')
- `-h`: show usage information

## Performance

RapidLLaMA achieves a generation speed of approximately 25-30 tokens/s for an 8-bit quantized 7B model running on the following CPU configuration:

```text
Architecture:            x86_64
Model name:              Intel(R) Xeon(R) Platinum 8350C CPU @ 2.60GHz
CPU(s):                  112
Thread(s) per core:      2
Core(s) per socket:      28
Socket(s):               2
```
![image](https://github.com/CoderLSF/RapidLLaMA/assets/65639063/d4477fcb-96fb-4b0a-a1fd-30ca583d0aa2)
For more details on the CPU configuration, refer to the [performance section](#performance) provided above.

## License

RapidLLaMA is licensed under the [Apache 2 License](LICENSE).

## Acknowledgements

We would like to express our gratitude to all contributors and users of RapidLLaMA. Your support and feedback have been invaluable in making this project a success. If you encounter any issues or have any suggestions, please feel free to open an issue on the GitHub repository.

## Contact
Email: [📩topcoderlsf@gmail.com](topcoderlsf@gmail.com)
Contact me if you any questions.
