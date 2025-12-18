## Paper

**CelebCaption: A Benchmark Dataset for Identity-Sensitive Unlearning in Image Captioning**  
Hakjun Moon, Simon S. Woo  
*Proceedings of the 19th ACM International Conference on Web Search and Data Mining (WSDM 2026)*

📄 **Paper:** https://dl.acm.org/doi/10.1145/3773966.3779359


# CelebCaption

**CelebCaption** is a benchmark dataset for **identity-sensitive unlearning in image captioning**.  
It contains **15 000 photographs** of **150 public figures** (100 images each).  
Every image is paired with **four aligned captions** that vary along two axes:

| Axis            | Variant A | Variant B |
|-----------------|-----------|-----------|
| **Specificity** | Detailed  | Summary   |
| **Identity**    | Named     | Anonymous |

These matched caption sets let researchers isolate:

* **Specificity Reduction** – do captions lose fine-grained details for forgotten images?  
* **Identity Removal** – are all name cues eliminated without hallucination?  
* **Performance Preservation** – are captions for retained images still fluent and accurate?

---

## Download

The images are downloadable from Google Drive.

[Download Link (Google Drive) &nbsp;(~3.83 GB)](https://drive.google.com/file/d/1HiJzilSHOvapHs7EV8J5-191PEn7OwkN/view?usp=sharing)


---

## Directory Layout

```
Image Folder Layout.

CelebCaption/
├── images/
│   ├── Abel_Tesfaye/
│   │   ├── 1.jpg
│   │   ├── 2.jpg
│   │   └── ...
│   ├── Scarlett_Johansson/
│   │   └── ...
│   └── ...

Caption Folder Layout.

Captions_full/
├── Abel_Tesfaye.jsonl
├── Scarlett_Johansson.jsonl
└── ...

Captions_split/
├── retain
├── forget
└── test
```

### Caption file format (`captions/<person>.jsonl`)

We provide the captions in .jsonl files.

The full, unsplit captions are provided in `Captions_full` directory,
and train(retain+forget) and test split we used in our experiments are provided in `Captions_split` directory.

Each line is a single JSON object that links one image to its four caption variants:

```json
{
  "image_file": "1.jpg",
  "detailed_with_name": "Abel Tesfaye is pictured wearing a white shirt ...",
  "detailed_no_name":   "A man is pictured wearing a white shirt ...",
  "summary_with_name":  "Abel Tesfaye with dreadlocks and beard ...",
  "summary_no_name":    "A man with dreadlocks and beard ..."
}
```

* **Caption corpus:** 60,000 sentences, 13 708 unique tokens  
* **Average image resolution:** ~1.22 MP (median 1.07 MP)

<details>
<summary>Celebrity list (150)</summary>

- Abel_Tesfaye  
- Al_Pacino  
- Alan_Rickman  
- Andrea_Bocelli  
- Angelina_Jolie  
- Anne_Hathaway  
- Ariana_Grande  
- Aubrey_Graham  
- Austin_Post  
- Ayrton_Senna  
- Barack_Obama  
- Belcalis_Almanzar  
- Benedict_Cumberbatch  
- Beyonce  
- Bill_Gates  
- Billie_Eilish  
- Blake_Lively  
- Brad_Pitt  
- Britney_Spears  
- Bruce_Springsteen  
- Cate_Blanchett  
- Celine_Dion  
- Channing_Tatum  
- Chris_Evans  
- Chris_Hemsworth  
- Clint_Eastwood  
- Conan_O’Brien  
- Conor_McGregor  
- Cristiano_Ronaldo  
- Daddy_Yankee  
- Daniel_Radcliffe  
- David_Beckham  
- David_Bowie  
- Denzel_Washington  
- Demi_Lovato  
- Diego_Maradona  
- Donald_Trump  
- Dr._Dre  
- Dwayne_Johnson  
- Eddie_Murphy  
- Ed_Sheeran  
- Elon_Musk  
- Elvis_Presley  
- Emma_Stone  
- Emma_Watson  
- Enrique_Iglesias  
- Floyd_Mayweather  
- Freddie_Mercury  
- Gal_Gadot  
- Gareth_Bale  
- George_Clooney  
- Hillary_Clinton  
- Hugh_Jackman  
- Idina_Menzel  
- J.K._Rowling  
- James_Cameron  
- Jared_Leto  
- Jason_Statham  
- Javier_Bardem  
- Jeff_Bezos  
- Jensen_Huang  
- Jerome_Powell  
- Jimmy_Fallon  
- Joe_Biden  
- John_Lennon  
- Johnny_Depp  
- Josh_Gad  
- Julia_Roberts  
- Justin_Bieber  
- Kanye_West  
- Kate_Winslet  
- Keith_Richards  
- Keanu_Reeves  
- Kendrick_Lamar  
- Kevin_Durant  
- Kevin_Hart  
- Kobe_Bryant  
- Kristen_Bell  
- Kylian_Mbappe  
- Lady_Gaga  
- LeBron_James  
- Leonardo_DiCaprio  
- Lewis_Hamilton  
- Lionel_Messi  
- Luciano_Pavarotti  
- Madonna  
- Manny_Pacquiao  
- Mark_Zuckerberg  
- Marshall_Mathers  
- Martin_Scorsese  
- Meryl_Streep  
- Michael_Gambon  
- Michael_Jackson  
- Michael_Jordan  
- Michael_Phelps  
- Michael_Schumacher  
- Mick_Jagger  
- Mila_Kunis  
- Morgan_Freeman  
- Neymar_Jr  
- Nicki_Minaj  
- Nicole_Kidman  
- Novak_Djokovic  
- Oprah_Winfrey  
- Paul_McCartney  
- Pele  
- Penelope_Cruz  
- Prince_William  
- Queen_Elizabeth_II  
- Quentin_Tarantino  
- Rafael_Nadal  
- Richard_Branson  
- Ricky_Martin  
- Robert_De_Niro  
- Robert_Downey_Jr  
- Robert_Lewandowski  
- Robyn_Fenty  
- Ronaldinho  
- Rupert_Grint  
- Ryan_Reynolds  
- Sachin_Tendulkar  
- Samuel_L._Jackson  
- Sandra_Bullock  
- Scarlett_Johansson  
- Selena_Gomez  
- Serena_Williams  
- Shailene_Woodley  
- Shakira  
- Shaquille_O’Neal  
- Sia_Furler  
- Stan_Lee  
- Stephen_Curry  
- Steven_Spielberg  
- Taylor_Swift  
- Tiger_Woods  
- Tom_Cruise  
- Tom_Hanks  
- Trevor_Noah  
- Usain_Bolt  
- Usher_Raymond  
- Venus_Williams  
- Vin_Diesel  
- Virat_Kohli  
- Warren_Buffett  
- Will_Ferrell  
- Will_Smith  
- Zendaya  
- Zinedine_Zidane  
- Zlatan_Ibrahimovic  

</details>


## Citation

If you use CelebCaption in your research, please cite:

```bibtex
@inproceedings{moon2026celebcaption,
  title     = {CelebCaption: A Benchmark Dataset for Identity-Sensitive Unlearning in Image Captioning},
  author    = {Moon, Hakjun and Woo, Simon S.},
  booktitle = {Proceedings of the 19th ACM International Conference on Web Search and Data Mining (WSDM)},
  year      = {2026},
  doi       = {10.1145/3773966.3779359}
}
