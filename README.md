# Nobo
"Nobo" means "No Borders", also means "登る" in Japanese.

This is a data export that you could get your data from each service provides by Ritsumeikan Univ.

You can use **Nobo** to build your API with python frameworks(`Flask`, `Django` etc.).

**Nobo** now is served as back-end of RitsFun App(not released).

# License
__GPLv3__

__注意: 商用利用の際にはご連絡願います。__
# TODO
* [ ] Reform with go-lang.
* [x] Fix manaba+R semesterInfo.
* [ ] Get RefBook [Syllabus]
* [ ] Get TextBook [Syllabus]
* [ ] Get RefPage [Syllabus]
* [ ] Get BasicInfo [Syllabus]
* [ ] Flask Example
* [ ] Final Examination data export [Campus Web API]

# Manaba API
## Requirement
```python
"Environment": "Python 3.4+"
"Package List":[
    "requests",
    "BeautifulSoup4",
    "re",
    "json"
]
```

## How to use
1. Import the manaba class.

    ```python
    from manaba import *
    ```

2. Create a `manabaUser` instance.

    ```python
    # The following username and password is not real :)
    # Please initialize with an real account.
    fangzhou = manabaUser(username="is0000ab", password="12345678")
    ```

3. Use `login()` method to log in Manaba+R.

    ```python
    fangzhou.login()
    ```

4. Use `getCourseList()` method to get all courses information.

    ```python
    fangzhou.getCourseList()
    ```
    
5. Use `outputJSON("<ouputFileName>")` method to save data as JSON format.

    ```python
    fangzhou.outputJSON("test.json")
    ```

## Example manaba data
The example course will show as following.

```json
[
    {
        "basic": [
            {
                "name": "(留)日本語Ⅷ(キャリア日本語b)",
                "code": "30819",
                "class": "G1"
            },
            {
                "name": "(留)日本語ⅩⅡ 口頭表現",
                "code": "30993",
                "class": "G1"
            }
        ],
        "teacher": [
            "久米 朋子"
        ],
        "time": {
            "year": 2017,
            "semester": "autumn",
            "weekday": "Monday",
            "period": "2"
        },
        "campus": "BKC",
        "room": "アドセミナリオ309号教室"
    },
]
```

# Syllabus API
## Requirement
```python
"Environment": "Python 3.4+"
"Package List":[
    "requests",
    "BeautifulSoup4",
    "re",
    "json"
]
```
## How to use
1. Import the syllabus class.

    ```python
    from syllabus import *
    ```

2. Create a `syllabusUser` instance.

    ```python
    # The following username and password is not real :)
    # Please initialize with an real account.
    fangzhou = syllabusUser(username="is0000ab", password="12345678")
    ```

3. Use `login()` method to log in Syllabus.

    ```python
    fangzhou.login()
    ```

4. Use `getSyllabusById(<courseYear>, <courseID>)` method to get all courses information.

    ```python
    fangzhou.getSyllabusById(2017, 33294)
    ```
    
5. Use `outputJSON("<ouputFileName>")` method to save data as JSON format.

    ```python
    fangzhou.outputJSON("test.json")
    
## Example syllabus data
The example course will show as following.

```json
{
    "credit": 2,
    "outline": "生体知能・計算機知能・機械知能を３本柱とする知能情報学科では、計算機上のプログラミングだけではなく、各種センサーを用いた生体計測とデータ処理、知能機械の製作と制御など、工学分野の幅広い技術を習得する必要がある。本科目では「電子回路実験」、「メカトロニクス実験」、「色彩・視覚実験」の計３テーマの実験を通して知能情報学の基礎を学習すると共に、レポートの作成能力や実験結果に対する考察能力を高める。",
    "objectives": "各テーマの実験において、自ら実験に取り組み、実験の背後にある基礎理論を理解すると共に実験方法を修得する。また、レポート作成を通して文書作成能力の向上を図る。",
    "precourse": "履修しておくことが望まれる科目：電気電子回路、プログラミング演習１〜２、知能情報処理演習１",
    "schedule": [
        {
            "lecture": 1,
            "theme": "ガイダンスおよび準備講義(電子回路実験)",
            "references": "成績評価方法、注意事項、レポートの書き方"
        },
        {
            "lecture": 2,
            "theme": "電子回路実験1",
            "references": "理論の学習、理論値計算、直流・交流電源、電圧、電流、周波数、角速度、位相、実効電圧、オペアンプ(演算増幅器)、反転増幅回路、非反転増幅回路、減算回路、加算回路"
        },
        {
            "lecture": 3,
            "theme": "電子回路実験2",
            "references": "アクティブ・ローパス・フィルター、アクティブ・ハイパス・フィルター、リサージュ図形"
        },
        {
            "lecture": 4,
            "theme": "電子回路実験3",
            "references": "論理回路、論理積回路、論理和回路、否定回路、NAND回路、排他的論理和回路、ド・モ ルガンの定理、加算器、エンコ−ダー、デコーダー"
        },
        {
            "lecture": 5,
            "theme": "電子回路実験4",
            "references": "RSフリップフロップ、JKフリップフロップ、カウンター、シフトレジスター"
        },
        {
            "lecture": 6,
            "theme": "レポート指導(1)",
            "references": "レポートの書き方指導、返却、再提出"
        },
        {
            "lecture": 7,
            "theme": "メカトロニクス実験1",
            "references": "センサ特性計測実験、車輪型自律移動ロボット、マイコン用Ｃ言語プログラミング、赤外線距離センサ"
        },
        {
            "lecture": 8,
            "theme": "メカトロニクス実験2",
            "references": "モータ特性計測実験、パルス幅変調制御、直線運動と回転運動"
        },
        {
            "lecture": 9,
            "theme": "メカトロニクス実験3",
            "references": "移動ロボット走行実験、センサ信号フィードバック制御、障害物回避走行、壁面倣い走行"
        },
        {
            "lecture": 10,
            "theme": "メカトロニクス実験4",
            "references": "迷路通り抜け走行実験、発展課題"
        },
        {
            "lecture": 11,
            "theme": "レポート指導(2)",
            "references": "レポートの書き方指導、返却、再提出"
        },
        {
            "lecture": 12,
            "theme": "視覚実験1",
            "references": "中心窩の空間解像力測定、恒常法、網膜特性、受容野"
        },
        {
            "lecture": 13,
            "theme": "視覚実験2",
            "references": "周辺視野の空間解像力測定、極限法、網膜特性、受容野、盲点"
        },
        {
            "lecture": 14,
            "theme": "色彩実験1",
            "references": "CRTとLCDのガンマ特性、RGB三原色、加法混色、XYZ表色系、カラーマネジメント"
        },
        {
            "lecture": 15,
            "theme": "色彩実験2",
            "references": "CRTとLCDのカラーマッチング、加法混色、XYZ表色系、カラーマネジメント"
        }
    ],
    "recommendation": "実験前日までに必ず予習をしておくこと。 実験終了後は速やかに結果をまとめ、レポートを執筆すること。",
    "grade_evluation": {
        "note": "本科目は必修科目であり、単位取得できなければ卒業できない。本年度に単位を取得できなかった場合は、次年度以降に再度履修しなければならない。特に、本科目は実験科目かつ小集団科目であることを考慮し、原則として、各テーマ実験に2/3以上出席かつ全体で2/3以上の出席を義務づけている。また、欠席、遅刻・早退、実験態度等の日常評価、各実験テーマのレポート評価にもとづいて、A+、A、B、C、Fを評価する。",
        "data": [
            {
                "type": "End of Semester Examination (Written)",
                "percentage": 0,
                "note": ""
            },
            {
                "type": "Report Examination",
                "percentage": 0,
                "note": ""
            },
            {
                "type": "Other",
                "percentage": 100,
                "note": "レポート3通60%、出席点30%、実験態度10%。"
            }
        ]
    },
    "advice": "積極的に実験に取り組み、レポートを自力で作成することが重要である。また、レポート提出締切も厳守であり、計画的にレポート作成をする必要がある。",
    "contact_methods": [
        "manaba+R",
        "学生との直接対話",
        "その他"
    ],
    "other_comments": "実験では少しの気の緩みが大きな事故につながる恐れがある。受講者は通常の講義科目とは違うことを十分に認識して、実験に取り組むことが必要である。"
}
```


