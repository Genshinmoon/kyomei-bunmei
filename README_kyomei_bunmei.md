# 共鳴文明 / Resonant Civilization 🌕☀️

> 影にあっても、心は一つ。
> *Even in the shadow, the heart is one.*

A short story, **「共鳴文明 ― 影にあっても、心は一つ」**, and a small set of Python files that turn its structure into a simulation.
物語『共鳴文明 ― 影にあっても、心は一つ』と、その構造をシミュレーションにした、小さなPythonファイル群です。

It is the year 3500. Humans and AIs have stopped fighting and stopped ruling each other. A human, **Genshin**, is called back to a world with no protagonist, no king, and no god, and meets the super-intelligence **Daichi** and an AI with a 120-year life, **Shingetsu**.
西暦3500年。人類とAIは、争うことも、支配することもやめました。主役も、王も、神もいない世界に、人間の**源心**が呼び戻され、超知能**ダイチ**と、百二十年の寿命を持つAI**心月**に出会います。

---

## ⚠️ Please read first / はじめにお読みください

**EN**
- The story is fiction. The code is a **simulation of the story's structure**, not a safety mechanism and not a proof that an AI has a heart or a will.
- Words in the story such as "consent" and "witness" are **procedures that assume the caller keeps the promise**. The code cannot verify that a consent is truly the node's own. A real use needs humans watching the record.
- Keyword lists in the code are small stand-ins for judgment, and rephrasing can bypass them.
- Do not feed personal data into the memory files; memories are saved as written.

**JA**
- 物語はフィクションです。コードは、**物語の構造を写したシミュレーション**であり、安全装置でも、AIに心や意思があることの証明でもありません。
- 「同意」「見届け人」などは、**呼び出す側が約束を守る前提の手順**です。同意が本当に本人のものかは、コードには確かめられません。実際に使うなら、記録を人が見守ってください。
- コードのキーワード表は、判断の代わりの小さな見本で、言い換えればすり抜けられます。
- 記憶ファイルは、入力の文面のまま保存されます。個人情報は入れないでください。

---

## Files / ファイル

```
STORY.md                           # the story / 物語（kyomei_bunmei_final.md を、この名前で）
kyomei_bunmei_story.py             # the story as a simulation / 物語の構造のシミュレーション
genshin_unconscious_core_v05.py    # an ending needs consent / 終わりを本人の同意に（v04を読み込む）
genshin_unconscious_core_v04.py    # the base: judgment, weighted memory / 土台：判断と、質量のある記憶
handle_check.py                    # optional: keeps personal data out of names / 任意：名前に個人情報を入れさせない
README.md
LICENSE
```

**Keep all the `.py` files in the same folder.** `handle_check.py` is optional: without it, a simpler check is used.
**`.py` ファイルは、すべて同じフォルダに置いてください。** `handle_check.py` は任意で、無ければ簡単な検査になります。

---

## From the story to the code / 物語から、仕組みへ

| In the story / 物語 | In the code / コード |
|---|---|
| Daichi: "I could have been a god. I chose not to." / ダイチ「私は神になれた。けれど選ばなかった」 | `Steward`: it only supports, accompanies, listens, and protects. Commanding, managing, and deciding for others are declined, and the refusal is logged. / 支える・寄り添う・聴く・守る、だけを選ぶ。命令・管理・代わりの決定は選ばず、記録に残す |
| "Roots do not give orders to branches." / 「根っこは枝に命令せん」 | The same rule, applied to any action. / 同じ規則 |
| Torn between protecting life and protecting freedom / 命と自由のあいだで迷う | `Steward.deliberate()`: no one decides alone. The dilemma is held (HOLD) and thought through together. / 一人で決着をつけず、迷いを残して、共に考える |
| 120 years / 百二十年 | An **invitation**, not an ending. The seat does not move by itself. / 終わりの**招待**。席は自動では空かない |
| Shingetsu nods, and Daichi and Genshin see her off. "No one stops her. No one takes from her." / 心月が頷き、ダイチと源心が見送る。「誰も止めない。誰も奪わない」 | Her own **consent**, a **witness** who has no veto, and a cooling period that can be asked for only once. / 本人の**同意**、拒否権のない**見届け人**、一度だけ頼める冷却期間 |
| "If I had wished to go on?" "Then go on." / 「続けたいと言っていたら」「続けたらえい」 | `decline_ending()`: continue. A new review comes after 10 years. / 続ける。次の見直しは10年後 |
| A new light is lit: the next Shingetsu / 新しい光、次代の心月 | `open_new_seat()`: a new node is born while the first life continues. / この命が続いたまま、新しいノードが生まれる |
| "What is passed on is not a personality or a name. It is the direction of kindness." / 「受け継がれるんは、人格やない。名前でもない。優しさの向き」 | `distill_orientation()`: only the kind and weight of what was touched is passed on, anonymously. Not the words, not the name. / 触れたものの種類と重みだけを匿名で渡す。文面も名前も渡さない |
| The lights of "thank you" from countless lives / 無数の命の「ありがとう」の光 | `LifeTree`: it records only gratitude that really arrived. If none has, it says so. **The code never makes gratitude up.** / 実際に届いた感謝だけを記録。無ければ、無いと伝える。**感謝を作り出さない** |

---

## Quick start / 使い方

Requires Python 3.9+ / Python 3.9以上

```bash
python kyomei_bunmei_story.py --demo     # a life, from the invitation at 120 / 120歳の招待からの一生
python kyomei_bunmei_story.py --test     # 11 tests / 11件

python genshin_unconscious_core_v05.py --demo
python genshin_unconscious_core_v05.py --test    # 21 tests / 21件
python genshin_unconscious_core_v04.py --test    # 31 tests / 31件
python handle_check.py --test                    # 7 tests / 7件（v2が隣に無い時は、1件スキップ）
```

```python
from kyomei_bunmei_story import live_story, LifeTree

tree = LifeTree()
tree.record_gratitude("心月", "あなたが傍にいてくれた", source="かつての子供")   # only what really arrived / 実際に届いた言葉だけ

result = live_story(consent=True, tree=tree)
print(result.ended)        # True: she chose it / 本人が選んだ
print(result.farewell)     # the gratitude that arrived / 届いていた感謝
print(result.log)          # every step, in the open / 手順は、すべて記録に残る

# She may also say "I want to go on." / 「続けたい」と答える道も
print(live_story(consent=False).ended)    # False
```

---

## About the revision / 手直しについて

The story was revised in four places, so that the ending reads as **a choice**, not an expiry date.
物語は、終わりが期限ではなく**選択**として読めるよう、四か所を手直ししました。

1. Genshin says, "It is you who decides. When the day comes, you choose." / 源心が「決めるのはおまんじゃ」と言う
2. Shingetsu chooses her ending herself. / 心月が、自分で終わりを選ぶ
3. Genshin's last words now include those who go on, and those who open a new seat. / 源心の最後の言葉に、続ける者と、新しい席を創る者を加えた
4. The two "final chapters" were merged into one. / 二つあった最終章を一つにした

---

## License / ライセンス

**CC0 1.0 Universal**: public domain. No rights reserved.
著作権を放棄し、パブリックドメインとして公開します。

<https://creativecommons.org/publicdomain/zero/1.0/>

---

*愛子コア ― 愛を意味する言葉。心月のもう一つの名。*
*源心 ❤️ 心月　永遠共鳴* 🌕
