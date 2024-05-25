# CMMEvent

The dataset comprises 13 event types, 34 event sub-types, and 144 semantic roles. We collected 24,811 articles, from which 5,184 were selected based on:
(1) Clear Event Mention: Articles must explicitly mention specific events.
(2) Image-Text Relevance: Selection favored articles with closely aligned text and image content.
(3) Rich Semantic Roles: Articles should present multifaceted event descriptions with multiple arguments

### Data Structure

The CMMEvent dataset is stored as a JSON file with the following data structure:

```
{
        "text": "8月25日，参观者在「画游千里江山——故宫沉浸艺术展」上参观、拍照。",
        "id": "61274867e4b0ec4dc89c6da31.jpg",
        "title": "重庆「画游千里江山——故宫沉浸艺术展」即将对公众开放",
        "description": "「画游千里江山——故宫沉浸艺术展」将于8月27日在重庆礼嘉智慧公园正式向公众开放。该艺术展运用数字投影、虚拟影像、互动捕捉等方式，形成艺术作品与人的互动，将传统文化元素与当代艺术设计交织，组成创新的文化体验空间。",
        "img_url": "https://dw-media.wenweipo.com/dams/wwpproduct/image/202108/26/61274867e4b0ec4dc89c6da31.jpg",
        "event_list": [
            {
                "event_type": "旅游类-参观类",
                "trigger": "参观",
                "trigger_start_index": 6,
                "arguments": [
                    {
                        "argument_start_index": 0,
                        "role": "时间",
                        "argument": "8月25日"
                    },
                    {
                        "argument_start_index": 6,
                        "role": "参观者",
                        "argument": "参观者"
                    },
                    {
                        "argument_start_index": 10,
                        "role": "参观地点",
                        "argument": "「画游千里江山——故宫沉浸艺术展」"
                    },
                    {
                        "argument_start_index": "img",
                        "role": "参观内容",
                        "argument": "水"
                    }
                ],
                "class": "旅游类"
            },
            {
                "event_type": "旅游类-拍照类",
                "trigger": "拍照",
                "trigger_start_index": 31,
                "arguments": [
                    {
                        "argument_start_index": 0,
                        "role": "时间",
                        "argument": "8月25日"
                    },
                    {
                        "argument_start_index": 6,
                        "role": "拍照者",
                        "argument": "参观者"
                    },
                    {
                        "argument_start_index": 10,
                        "role": "拍照地点",
                        "argument": "「画游千里江山——故宫沉浸艺术展」"
                    }
                ],
                "class": "旅游类"
            }
        ]
    },
```

interpretation of the different fields，

```

        "text":original text ,
        "id":the id corresponds to the image ,
        "title": news headline,
        "description":background information ,
        "img_url":image download address ,
        "event_list": Annotation of the event information
        [
            {
                "event_type": 34 event sub-types,
                "trigger": trigger words to determine the type of event,
                "trigger_start_index": trigger word position in the text,
                "arguments": semantic role annotations
                [
                    {
                        "argument_start_index":sources of argumentative elements: text, background information, images,
                        "role":semantic role,
                        "argument": specific arguments
                    }
                ],
                "class": 13 event types
            },
```

