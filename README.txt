LATENT LANGUAGE in LARGE LANGUAGE MODELS

Custom sampling technique to produce text which, at any point, is likely to be
followed by a latent word, e.g. "joy".

To run:
> wget https://huggingface.co/karpathy/tinyllamas/resolve/main/stories15M.bin
> make
> ./run stories15M.bin -n 10 -l "joy"     

Forked off of https://github.com/karpathy/llama2.c
Removed a bunch of files to better understand the core inference functions.

