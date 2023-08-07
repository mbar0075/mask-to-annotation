**<h1>mask-to-annotation</h1>**
<!-- Describe the software -->
**mask-to-annotation** is a powerful and efficient tool for automatically generating annotations in popular computer vision formats such as COCO, YOLO, and VGG from saliency masks.

By leveraging contour detection algorithms and image processing techniques, our software automates the annotation process, saving valuable time and effort.



<hr>

**<h2 name="coco-annotations">Table of Contents</h2>**

- **[Examples](#examples)**
  - [Visual Annotations](#visual-annotations)
  - [COCO Annotations](#coco-annotations)
  - [YOLO Annotations](#yolo-annotations)
  - [VGG Annotations](#vgg-annotations)
- **[Backend](#backend)**
  - [Annotation Generation Pipeline](#annotation-pipeline)

<hr>

**<h1 name="examples">Examples</h1>**

**<h2 name="visual-annotations">Visual Annotations</h2>**
<!-- Show images -->
<h3>Sample Images</h3>

<p align="center"><img src='./Evaluation/Figures/Original vs Mask Multiple.png'></p>


<h3>Polygon Annotation</h3>
<p align="center"><img src='./Evaluation/Figures/COCO_VGG_Results_Multiple.png'></p>

<h3>Bounding Box Annotation</h3>
<p align="center"><img src='./Evaluation/Figures/YOLO_Results_Multiple.png'></p>

**<h2 name="coco-annotations">COCO Annotations</h2>**
<!-- Show json output -->
<h3>Annotation (JSON)</h3>

```json
{
    "info": {
        "description": "COTSDataset"
    },
    "images": [
        {
            "id": 0,
            "width": 1280,
            "height": 720,
            "file_name": "souveniers_oc_3_colour_mask_1_mask.png"
        }
    ],
    "annotations": [
        {
            "id": 0,
            "iscrowd": 0,
            "image_id": 0,
            "category_id": 0,
            "segmentation": [
                [
                    ...
                ]
            ],
            "bbox": [
                ...
            ],
            "area": 32067.5
        }
    ],
    "categories": [
        {
            "id": 0,
            "name": "souvenirs_oc"
        }
    ]
}
```

<hr>

**<h2 name="yolo-annotations">YOLO Annotations</h2>**
<!-- Show txt output -->
<h3>Annotation (TXT)</h3>

```python
# souvenirs_no_3_colour_mask_1_mask.txt
0 0.69882812 0.65972222 0.32578125 0.48055555

# labels.txt
souvenirs_oc
```

<hr>

**<h2 name="vgg-annotations">VGG Annotations</h2>**
<!-- Show json output -->
<h3>Annotation (JSON)</h3>

```json
{
    "food_3_colour_mask_1_mask.png": {
        "fileref": "",
        "size": 1280,
        "filename": "food_3_colour_mask_1_mask.png",
        "base64_img_data": "",
        "file_attributes": {},
        "regions": {
            "0": {
                "shape_attributes": {
                    "name": "polygon",
                    "all_points_x": [
                        ...
                    ],
                    "all_points_y": [
                        ...
                    ]
                },
                "region_attributes": {
                    "label": "food_no"
                }
            }
        }
    }
}
```

<hr>

**<h1 name="backend">Backend</h1>**
**<h2 name="annotation-pipeline">Annotation Generation Pipeline</h2>**
```python
{annotation style}.py:

def mask_to_annotation(mask):
. . .

def display(im_dict, annotation_color):
. . .

def save(im_dict):
. . .

def annotate(im, do_display=True, do_save=True, annotation_color='g'):
. . .

```