# IMI2（政府相互運用性フレームワーク - GIF）

本リポジトリには、プロジェクト名**IMI2**として進められている、日本の**政府相互運用性フレームワーク（GIF）**に関するドキュメントが格納されています。GIFは、行政サービス間および官民間のデータ相互運用性を高めるために設計された、ルール、データモデル、および実践ガイドブックの集合体です。

- **公式ポリシーページ**: [政府相互運用性フレームワーク（GIF）](https://www.digital.go.jp/policies/data_strategy_government_interoperability_framework/)

## コアコンセプト

本フレームワークは、データが標準化されるだけでなく、実装において実用的であることを保証するため、階層化されたアーキテクチャに基づいて構築されています。相互運用性のための共通基盤を維持しつつ、特定のニーズに合わせて適用可能な参照モデル群を提供します。

### コアデータモデル
GIFの基盤は、一般的なエンティティに対する標準化されたデータモデル群であり、シームレスなデータ交換を可能にし、設計コストを削減します。これにより、既存の標準が統一されたフレームワークに統合されます。

- **目的**: 個人、法人、住所、施設などのエンティティに関する基本的なデータ構造を標準化すること。
- **主な構成要素**:
    - **コアデータパーツ**: 住所、日付、電話番号などの共通属性に対する統一フォーマットであり、一貫したデータ処理を確保します。
    - **構造化データ型**: ID、コード、役割などの複雑なデータに対する事前定義された構造であり、一貫性を維持します。
        - **ID情報型**: ID値とその分類（例：マイナンバー、従業員ID）を組み合わせたもの。
        - **コード情報型**: コードとその意味（例：性別コード "1" → "男性"）を関連付けるもの。
        - **役割関与情報型**: エンティティ間の関係（例：個人に紐づく「保護者」の役割）を定義するもの。
- **主要ドキュメント**:
    - [コアデータモデル全体概要](430_Core_Data_Model_Overview.md)
    - [クラス図](430-1_DMD_Class_Diagram.pdf)
    - [データモデル記述（DMD）スプレッドシート](438_Core_Data_Model_DMD.xlsx)

### 住所管理
住所データの取り扱いに対する標準化されたアプローチは、相互運用性において極めて重要です。GIFでは、正確性と一貫性を確保するため、コードを用いた管理を推奨しています。

- **推奨フォーマット（コード管理）**: **全国地方公共団体コード**および**町字ID**を使用して住所をプログラム的に表現し、テキスト表現の揺れを防ぎます。
    - *例*: `131016`（千代田区） + `0002002`（霞が関） + `1-6` → "東京都千代田区霞が関2-1-6"
- **テキストフォーマット**: テキストデータの場合、4項目の構造（都道府県、市区町村、町字、番地以下）が推奨されます。
- **英語フォーマット**: ヘボン式ローマ字の規則に従います。
    - *例*: `2-1-2 Kasumigaseki, Chiyoda-ku, Tokyo 100-8926, Japan`
- **主要ドキュメント**: [コアデータパーツ 住所（アドレス）](442_Core_Data_Part_Address.md)

### コード（分類体系）導入
GIFは、異なるシステム間でデータが一貫して分類されるように、コードの設計と利用に関するガイドラインを提供します。

- **コードの種類**:
    - **識別のためのコード**: 一意の識別子（例：マイナンバー、法人番号）。
    - **分類のためのコード**: カテゴリ分けのためのコード（例：性別のISO 5218、日本標準産業分類）。
- **設計原則**:
    - **既存の標準を優先**: 適用可能な場合はISOやJISのコードを使用します。
    - **有意コードと無意コード**: 意味情報を持たせたコード（例：`JP-CAS-2017-003`）と、柔軟でランダム化されたコード（例：UUID）のいずれかを選択します。
    - **エラー防止**: 重要なコードにはチェックディジットを使用し、入力ミスを防止します。
- **主要ドキュメント**: [コード（分類体系）導入実践ガイドブック](463-1_Practical_Guidebook_for_Code_(Classification_System)_Implementation.md)

---

## 全ドキュメント

### 全体概要
- [410_GIF_Whole.md](410_GIF_Whole.md)
- [411_GIF_Explanation.pdf](411_GIF_Explanation.pdf) ([pptx](411_GIF_Explanation.pptx))

### コア語彙
- [420_Core_Vocabulary.md](420_Core_Vocabulary.md)

### コアデータモデル
- [430_Core_Data_Model_Overview.md](430_Core_Data_Model_Overview.md)
- [430-1_DMD_Class_Diagram.pdf](430-1_DMD_Class_Diagram.pdf)
- [431_Core_Data_Model_Description_Individual.md](431_Core_Data_Model_Description_Individual.md)
- [432_Core_Data_Model_Description_Contact.md](432_Core_Data_Model_Description_Contact.md)
- [433_Core_Data_Model_Description_Address.md](433_Core_Data_Model_Description_Address.md)
- [434_Core_Data_Model_Description_Corporation.md](434_Core_Data_Model_Description_Corporation.md)
- [435_Core_Data_Model_Description_Facility.md](435_Core_Data_Model_Description_Facility.md)
- [436_Core_Data_Model_Description_Accessibility.md](436_Core_Data_Model_Description_Accessibility.md)
- [437_Core_Data_Model_Description_Childcare_Support_Information.md](437_Core_Data_Model_Description_Childcare_Support_Information.md)
- [438_Core_Data_Model_DMD.pdf](438_Core_Data_Model_DMD.pdf) ([xlsx](438_Core_Data_Model_DMD.xlsx))

### コアデータパーツ
- [441_Core_Data_Part_Date_Time.md](441_Core_Data_Part_Date_Time.md)
- [442_Core_Data_Part_Address.md](442_Core_Data_Part_Address.md)
- [443_Core_Data_Part_Postal_Code.md](443_Core_Data_Part_Postal_Code.md)
- [444_Core_Data_Part_Geo_Information.md](444_Core_Data_Part_Geo_Information.md)
- [445_Core_Data_Part_Phone_Number.md](445_Core_Data_Part_Phone_Number.md)

### 実装データモデル - 行政
- [451-1_Implementation_Data_Model_Application.md](451-1_Implementation_Data_Model_Application.md)
- [451-1-1_Application_(Individual)_Data_Model.md](451-1-1_Application_(Individual)_Data_Model.md)
