LATENT LANGUAGE in LARGE LANGUAGE MODELS

"Look forward" sampling technique to produce text which, at any point, is
likely to be followed by a latent word, e.g. "joy".

The core idea is:
> latent_word = "joy"
> text = ""
>
> while True:
>
>     max_word = ""
>     max_p = 0
>
>     for token, prob in LLM(text).items():
>         subsequent_predictions = LLM(text + token)
>         prob_latent = subsequent_predictions[latent_word]
>
>         if prob * prob_latent > max_p:
>             max_word = token
>             max_p = prob * prob_latent
>             
>     text += max_word


To run:
> wget https://huggingface.co/karpathy/tinyllamas/resolve/main/stories15M.bin
> make
> ./run stories15M.bin -n 10 -l "joy"     

Forked off of https://github.com/karpathy/llama2.c
Removed a bunch of files to better understand the core inference functions.
