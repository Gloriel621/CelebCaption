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

The full dataset (~3.83 GB) is on Google Drive:

```
https://drive.google.com/file/d/1HiJzilSHOvapHs7EV8J5-191PEn7OwkN/view?usp=sharing
```

---

## Directory Layout

```
CelebCaption/
├── images/                       # JPEG photos
│   ├── Abel_Tesfaye/
│   │   ├── 1.jpg
│   │   ├── 2.jpg
│   │   └── ...
│   ├── Scarlett_Johansson/
│   │   └── ...
│   └── ...
└── captions/                     # one .jsonl file per person
    ├── Abel_Tesfaye.jsonl
    ├── Scarlett_Johansson.jsonl
    └── ...
```

### Caption file format (`captions/<person>.jsonl`)

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

* **Caption corpus:** 100 000 sentences, 13 708 unique tokens  
* **Average image resolution:** ~1.22 MP (median 1.07 MP)
