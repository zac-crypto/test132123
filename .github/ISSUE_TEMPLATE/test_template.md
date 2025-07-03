---
name: new retargeting ad
about: 追蹤新 retargeting ad 的進度
title: "[new retargeting ad]: <placement_name>"
body:
  - type: input
    id: placement_name
    attributes:
      label: 新 Placement 的名稱
      placeholder: gliaaffiliate_beaulace

  - type: input
    id: base_placement_url
    attributes:
      label: 要依照此 Placement 的設定（可選）
      placeholder: https://gstudio.gliacloud.com/admin/ad/placement/845/change/

  - type: input
    id: adtag_url
    attributes:
      label: adtag_url 格式組合（可照預設）
      placeholder: https://player.gliacloud.com/vast/GAM_CREATIVE?video={video}&click={click}

  - type: input
    id: video_url
    attributes:
      label: Video URL
      placeholder: https://...

  - type: input
    id: click_url
    attributes:
      label: Click URL
      placeholder: https://...

  - type: textarea
    id: retargeting_rule_text
    attributes:
      label: Retargeting Rule（文字說明，或要仿照某個 adunit 的 retargeting_rule 可以貼那個 adunit 的 url）
      placeholder: 範例：已看過首頁 + 滯留 5 秒

  - type: textarea
    id: slots
    attributes:
      label: 要加入 Placement 的 Slots
      placeholder: 
---

# Checklist
- [ ] 建立新 Placement: {new_placement_url}

- [ ] 測試 adtag_url 
  - 複製 adtag_url  到[測試網站](https://googleads.github.io/googleads-ima-html5/vsi/)，
  - 點 test ad，確認影片是預期的影片，點擊導流是預期的連結。

- [ ] 將 retargeting rule 文本轉換為 JsonLogic: 
```json
```

- [ ] 撰寫 batch script:
  - reminder: retargeting_record_keys 要多加進 retargeting rule 用的 cookie name
```python3
# batch script
```

- [ ] batch script 與 @edwardlee23 or @mariafilippa double check

- [ ] 執行 batch script
```python3
# 執行結果
```

- [ ] 檢查與確認
  - 到客戶網站看 signal-snacks.gliastudios.com domain 底下有 cookie name 的 cookie 和值
  - 到其中一個 slot 的 get code 頁面，應該就要看到這次的 retargeting ad
    - (ad 不一定剛好是第一個，如果 slot 本身有限制廣告次數，就重整多試幾次)

{chrome_dev_tools_screenshot}
{retargeting_ad_screenshot}

- [ ] 設定完隔天 ({日期}) 至 [metabase](https://metabase.gliaoffice.com/question#eyJkYXRhc2V0X3F1ZXJ5Ijp7ImRhdGFiYXNlIjo3LCJ0eXBlIjoicXVlcnkiLCJxdWVyeSI6eyJzb3VyY2UtdGFibGUiOjM0MTYsImFnZ3JlZ2F0aW9uIjpbWyJzdW0iLFsiZmllbGQiLDc2Mzc1LHsiYmFzZS10eXBlIjoidHlwZS9JbnRlZ2VyIn1dXSxbInN1bSIsWyJmaWVsZCIsNzYzODgseyJiYXNlLXR5cGUiOiJ0eXBlL0ludGVnZXIifV1dXSwiYnJlYWtvdXQiOltbImZpZWxkIiw3NjM2NCx7ImJhc2UtdHlwZSI6InR5cGUvRGF0ZSIsInRlbXBvcmFsLXVuaXQiOiJkYXkifV0sWyJmaWVsZCIsNzYzNzIseyJiYXNlLXR5cGUiOiJ0eXBlL1RleHQifV0sWyJmaWVsZCIsNzYzOTEseyJiYXNlLXR5cGUiOiJ0eXBlL1RleHQifV1dLCJvcmRlci1ieSI6W1siZGVzYyIsWyJhZ2dyZWdhdGlvbiIsMF1dXSwiZmlsdGVyIjpbImFuZCIsWyJ0aW1lLWludGVydmFsIixbImZpZWxkIiw3NjM2NCx7ImJhc2UtdHlwZSI6InR5cGUvRGF0ZSJ9XSwtMSwiZGF5Il0sWyI9IixbImZpZWxkIiw3NjM3Mix7ImJhc2UtdHlwZSI6InR5cGUvVGV4dCJ9XSwiZ2xpYWFmZmlsaWF0ZV93d2JlYXJzIl1dfX0sImRpc3BsYXkiOiJsaW5lIiwiZGlzcGxheUlzTG9ja2VkIjp0cnVlLCJ2aXN1YWxpemF0aW9uX3NldHRpbmdzIjp7ImdyYXBoLmRpbWVuc2lvbnMiOlsic2xvdF9rZXkiXSwiZ3JhcGgubWV0cmljcyI6WyJzdW0iXSwiZ3JhcGguc2VyaWVzX29yZGVyX2RpbWVuc2lvbiI6bnVsbCwiZ3JhcGguc2VyaWVzX29yZGVyIjpudWxsfSwidHlwZSI6InF1ZXN0aW9uIn0=) 追蹤確認總投放次數，placement 記得換成新的 placement
  - (一開始可能次數比較少，但通常不會沒有)
