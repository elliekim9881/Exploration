# EX03 인물모드 문제점 찾기

# AIFFEL Campus Online Code Peer Review Templete
- 코더 : 김소연
- 리뷰어 : 이윤상


# PRT(Peer Review Template)
- [x]  **1. 주어진 문제를 해결하는 완성된 코드가 제출되었나요?**
    - 문제에서 요구하는 최종 결과물이 첨부되었는지 확인
    - 문제를 해결하는 완성된 코드란 프로젝트 루브릭 3개 중 2개, 
    퀘스트 문제 요구조건 등을 지칭
        - 아웃포커싱 효과가 적용된 인물모드 사진과 동물 사진, 배경전환 크로마키사진을 각각 1장 이상 성공적으로 제작하였다.
            - ![image](https://github.com/lys678/Exploration/assets/137245511/fa8931f6-8b4b-4701-b367-01d821f78c52)
            - ![image](https://github.com/lys678/Exploration/assets/137245511/6ccee3a1-5b5d-4ac3-aeee-04cb55ead662)
            - ![image](https://github.com/lys678/Exploration/assets/137245511/a7b23775-981d-46f4-8969-f8ab667cc003)
            - 루브릭의 모든 조건을 만족하는 사진들을 성공적으로 제작하였습니다.
     
        - 인물사진에서 발생한 문제점을 정확히 지적한 사진을 제출하였다.
            - ![image](https://github.com/lys678/Exploration/assets/137245511/92ee071b-de82-4575-b344-5ae9cc4972ba)
            - ![image](https://github.com/lys678/Exploration/assets/137245511/2f088889-fb0c-4b65-9f7f-c155854cbc09)
            - 문제점을 알아보기 쉽게 표기하였고, 설명을 통해 정확히 지적하였습니다.
              
        - semantic segmentation mask의 오류를 보완할 수 있는 좋은 솔루션을 이유와 함께 제시하였다.
            - ![image](https://github.com/lys678/Exploration/assets/137245511/ea56b344-5860-4fce-a730-4c31488e149d)
            - ![image](https://github.com/lys678/Exploration/assets/137245511/fe4bbe67-82cd-4735-83d4-396ef8472a26)
            - ![image](https://github.com/lys678/Exploration/assets/137245511/a99162d7-68ad-4dde-8142-b678d0e39284)
            - ![image](https://github.com/lys678/Exploration/assets/137245511/28cd851d-9193-41fa-8ad5-edaf1f9de581)
            - 이미지 처리에 사용되는 모폴로지 연산 중 Opening을 적용,  erode 연산 적용 등의 방법을 시도해보면서 직접 어떻게 수행하는 것이 좋은지를 잘 보여주었습니다.
            - 본인만의 이미지 처리 방법을 직접 구현하여 기존에 있던 문제점을 개선하였습니다. 




- [x]  **2. 전체 코드에서 가장 핵심적이거나 가장 복잡하고 이해하기 어려운 부분에 작성된 
주석 또는 doc string을 보고 해당 코드가 잘 이해되었나요?**
    - 해당 코드 블럭에 doc string/annotation이 달려 있는지 확인
    - 해당 코드가 무슨 기능을 하는지, 왜 그렇게 짜여진건지, 작동 메커니즘이 뭔지 기술.
    - 주석을 보고 코드 이해가 잘 되었는지 확인
        - ![image](https://github.com/lys678/Exploration/assets/137245511/1565e7d9-d323-4abb-97df-c0ccb0542200)
        - ![image](https://github.com/lys678/Exploration/assets/137245511/cf38f50c-4ac4-452f-af00-6dd018a3d0d9)
        - 각 기능들을 편리하게 하기 위해 함수를 많이 사용하였는데 주석을 이용하여 다른 사람이 이해하기 쉽도록 작성하였습니다.



        
- [x]  **3. 에러가 난 부분을 디버깅하여 문제를 “해결한 기록을 남겼거나” 
”새로운 시도 또는 추가 실험을 수행”해봤나요?**
    - 문제 원인 및 해결 과정을 잘 기록하였는지 확인
    - 문제에서 요구하는 조건에 더해 추가적으로 수행한 나만의 시도, 
    실험이 기록되어 있는지 확인
        - ![image](https://github.com/lys678/Exploration/assets/137245511/a2e4a5a2-e161-4baf-8777-cb0092d82348)
        - ![image](https://github.com/lys678/Exploration/assets/137245511/61ee90ba-5be9-4c48-be0a-2cdb8cc69b21)
        - 이미지 처리를 개선하면서 다양한 방법을 시도해 보았고 문제점을 개선하였습니다.


       
- [x]  **4. 회고를 잘 작성했나요?**
    - 주어진 문제를 해결하는 완성된 코드 내지 프로젝트 결과물에 대해
    배운점과 아쉬운점, 느낀점 등이 기록되어 있는지 확인
    - 전체 코드 실행 플로우를 그래프로 그려서 이해를 돕고 있는지 확인
        - ![image](https://github.com/lys678/Exploration/assets/137245511/3fb5bb43-864c-4edb-b13e-fcbc22cd1a80)
        - 회고에서 배운점과 아쉬운점이 잘 드러나있고, 느낀점 등이 기록되어있습니다.
        - 자신이 시도했던 방법들에 대해 피드백과 추가적인 기술들의 융합에 대해서도 잘 기록하였습니다.


        
- [x]  **5. 코드가 간결하고 효율적인가요?**
    - 파이썬 스타일 가이드 (PEP8) 를 준수하였는지 확인
    - 하드코딩을 하지않고 함수화, 모듈화가 가능한 부분은 함수를 만들거나 클래스로 짰는지
    - 코드 중복을 최소화하고 범용적으로 사용할 수 있도록 함수화했는지
        -  ![image](https://github.com/lys678/Exploration/assets/137245511/4509bb34-81a8-4b85-90fe-40388dc7b05c)
        -  ![image](https://github.com/lys678/Exploration/assets/137245511/9f3aee38-2e71-40ae-810a-0f44f3cb0468)
        -  ![image](https://github.com/lys678/Exploration/assets/137245511/8b0bf6c9-8999-49e7-b793-1fe7611dba24)
        - 코드를 간결하고 효율적으로 작성하였고, 함수의 사용을 통해 코드가 범용적으로 사용될 수 있도록 작성하였습니다.



# 참고 링크 및 코드 개선
```

```
