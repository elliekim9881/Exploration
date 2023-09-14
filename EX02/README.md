# EX02 뉴스기사 요약해보기
## used dataset : news_summary_more.csv [https://github.com/sunnysai12345/News_Summary]

# AIFFEL Campus Online Code Peer Review Templete
- 코더 : 김소연
- 리뷰어 : 이윤상


# PRT(Peer Review Template)
- [x]  **1. 주어진 문제를 해결하는 완성된 코드가 제출되었나요?**
    - 문제에서 요구하는 최종 결과물이 첨부되었는지 확인
    - 문제를 해결하는 완성된 코드란 프로젝트 루브릭 3개 중 2개, 
    퀘스트 문제 요구조건 등을 지칭
        - 분석단계, 정제단계, 정규화와 불용어 제거, 데이터셋 분리, 인코딩 과정이 빠짐없이 체계적으로 진행되었습니다.
        - ![image](https://github.com/lys678/Exploration/assets/137245511/d9f4d766-43a1-4b46-b6a1-970cc02f19a5)
        - ![image](https://github.com/lys678/Exploration/assets/137245511/8db60ea2-0bf3-4062-abf7-10994025186b)
        - ![image](https://github.com/lys678/Exploration/assets/137245511/9f612b48-ecf0-4b55-8596-d8df3d60e5b8)
        - 모델 학습이 진행되면서 train loss와 validation loss가 감소하는 경향을 그래프를 통해 확인했으며, 실제 요약문에 있는 핵심 단어들이 요약 문장 안에 포함되었습니다.
        - ![image](https://github.com/lys678/Exploration/assets/137245511/bd965fb1-37af-4ee3-93fe-cd17073b3499)
        - ![image](https://github.com/lys678/Exploration/assets/137245511/a37a750c-f0a8-4ce1-9394-faf7ba92a62b)
        - 두 요약 결과를 문법완성도 측면과 핵심단어 포함 측면으로 나누어 비교하고 분석 하였습니다.
        - ![image](https://github.com/lys678/Exploration/assets/137245511/e0550794-8d98-49d2-8e11-d6189c14826c)



- [X]  **2. 전체 코드에서 가장 핵심적이거나 가장 복잡하고 이해하기 어려운 부분에 작성된 
주석 또는 doc string을 보고 해당 코드가 잘 이해되었나요?**
    - 해당 코드 블럭에 doc string/annotation이 달려 있는지 확인
    - 해당 코드가 무슨 기능을 하는지, 왜 그렇게 짜여진건지, 작동 메커니즘이 뭔지 기술.
    - 주석을 보고 코드 이해가 잘 되었는지 확인
        - 초기 상태(initial_state)를 이전 시점의 상태로 사용하는 이유가 잘 설명되었습니다.
        - ![image](https://github.com/lys678/Exploration/assets/137245511/7f9c1eeb-753f-41dd-8893-2ff0e35b60f9)


        
- [X]  **3. 에러가 난 부분을 디버깅하여 문제를 “해결한 기록을 남겼거나” 
”새로운 시도 또는 추가 실험을 수행”해봤나요?**
    - 문제 원인 및 해결 과정을 잘 기록하였는지 확인
    - 문제에서 요구하는 조건에 더해 추가적으로 수행한 나만의 시도, 
    실험이 기록되어 있는지 확인
        - summa를 이용하여 추출적 요약을 시행하는 과정에서 ratio값에 따라 추출 요약이 출력되지 않는 문제를 여러가지 ratio값을 대입해보면서 분석했습니다.
        - ![image](https://github.com/lys678/Exploration/assets/137245511/c5903307-5355-4de4-91b8-b885d7c9ef5c)
        - ![image](https://github.com/lys678/Exploration/assets/137245511/ef0c16f4-e751-4af6-901f-0a252346beaf)

       
- [X]  **4. 회고를 잘 작성했나요?**
    - 주어진 문제를 해결하는 완성된 코드 내지 프로젝트 결과물에 대해
    배운점과 아쉬운점, 느낀점 등이 기록되어 있는지 확인
    - 전체 코드 실행 플로우를 그래프로 그려서 이해를 돕고 있는지 확인
        - 배운점, 아쉬운점, 느낀 점등이 잘 드러나고 아쉬운 부분들을 해결하기 위한 시도역시 잘 드러납니다.
        - 힉습 과정을 그래프화하여 이해하기 좋았습니다.
        - ![image](https://github.com/lys678/Exploration/assets/137245511/352022c1-b2e2-44be-aac9-c965c145f0a4)
        - ![image](https://github.com/lys678/Exploration/assets/137245511/0e44eea9-9c79-40d8-aa2c-3ca18d32931c)



        
- [X]  **5. 코드가 간결하고 효율적인가요?**
    - 파이썬 스타일 가이드 (PEP8) 를 준수하였는지 확인
    - 하드코딩을 하지않고 함수화, 모듈화가 가능한 부분은 함수를 만들거나 클래스로 짰는지
    - 코드 중복을 최소화하고 범용적으로 사용할 수 있도록 함수화했는지
        - 작업을 하는 도중 전처리 과정이 너무 오래 걸린다는 문제가 있었는데 이를 피클로 파일을 저장하는 방법을 통해 효율적으로 해결하였습니다.
        - ![image](https://github.com/lys678/Exploration/assets/137245511/6f06dafb-fa72-4ccc-8845-172c8218485a)



# 참고 링크 및 코드 개선
```
# 피클 파일로 저장하는 부분이 인상 깊었고 저도 이렇게 하면 작업에 효율이 더욱 증가할 것이라고 느꼈습니다.
https://wikidocs.net/8929
```
