# EX05 트랜스포머로 만드는 대화형 챗봇

# AIFFEL Campus Online Code Peer Review Templete
- 코더 : 김소연
- 리뷰어 : 이윤상


# PRT(Peer Review Template)
- [x]  **1. 주어진 문제를 해결하는 완성된 코드가 제출되었나요?**
    - 문제에서 요구하는 최종 결과물이 첨부되었는지 확인
    - 문제를 해결하는 완성된 코드란 프로젝트 루브릭 3개 중 2개, 
    퀘스트 문제 요구조건 등을 지칭
        - 해당 조건을 만족하는 코드를 캡쳐해 근거로 첨부
        - 1. 한국어 전처리를 통해 학습 데이터셋을 구축하였다.
             한국어 전처리를 통해 학습 데이터셋을 구축하였습니다.
             ![image](https://github.com/lys678/Exploration/assets/137245511/fd16f58a-7399-442c-b1c0-99d48d4a6978)
             ![image](https://github.com/lys678/Exploration/assets/137245511/6c9e0af1-2499-4006-9c2f-6441936254bc)
        - 2. 트랜스포머 모델을 구현하여 한국어 챗봇 모델 학습을 정상적으로 진행하였다.
             트랜스포머 모델을 구현하여 한국어 챗봇 모델 학습을 정상적으로 진행하였습니다.
             ![image](https://github.com/lys678/Exploration/assets/137245511/51e25db3-665d-46fb-8c12-33403c02ff5a)
             ![image](https://github.com/lys678/Exploration/assets/137245511/3a09dda8-840a-4786-992a-e88e2740ffb4)
        - 3. 한국어 입력문장에 대해 한국어로 답변하는 함수를 구현하였다.
             한국어 입력문장에 대해 한국어로 답변하는 함수를 구현하였습니다.
             ![image](https://github.com/lys678/Exploration/assets/137245511/28ce5def-ec9d-4233-8815-43b54ba9d09b)


- [X]  **2. 전체 코드에서 가장 핵심적이거나 가장 복잡하고 이해하기 어려운 부분에 작성된 
주석 또는 doc string을 보고 해당 코드가 잘 이해되었나요?**
    - 해당 코드 블럭에 doc string/annotation이 달려 있는지 확인
    - 해당 코드가 무슨 기능을 하는지, 왜 그렇게 짜여진건지, 작동 메커니즘이 뭔지 기술.
    - 주석을 보고 코드 이해가 잘 되었는지 확인
        - 잘 작성되었다고 생각되는 부분을 캡쳐해 근거로 첨부합니다.
        - 현재 이루어지는 작업을 잘 설명하였고 함수 내에서도 이해를 돕기 위해 주석을 적절히 작성하였습니다.
        - ![image](https://github.com/lys678/Exploration/assets/137245511/9f359d40-aee5-491d-8777-49fc5a9f2c57)
        
- [X]  **3. 에러가 난 부분을 디버깅하여 문제를 “해결한 기록을 남겼거나” 
”새로운 시도 또는 추가 실험을 수행”해봤나요?**
    - 문제 원인 및 해결 과정을 잘 기록하였는지 확인
    - 문제에서 요구하는 조건에 더해 추가적으로 수행한 나만의 시도, 
    실험이 기록되어 있는지 확인
        - 잘 작성되었다고 생각되는 부분을 캡쳐해 근거로 첨부합니다.
        - 주어진 질문만 하지 않고 여러 질문을하였고 나타난 문제들에 대해 원인을 분석하였습니다.
        - ![image](https://github.com/lys678/Exploration/assets/137245511/f75484de-ebf9-458f-b94f-abb4dc8c0ad1)
        - ![image](https://github.com/lys678/Exploration/assets/137245511/01d4e2b8-30ee-4635-a451-311b2dcc816f)

       
- [X]  **4. 회고를 잘 작성했나요?**
    - 주어진 문제를 해결하는 완성된 코드 내지 프로젝트 결과물에 대해
    배운점과 아쉬운점, 느낀점 등이 기록되어 있는지 확인
    - 전체 코드 실행 플로우를 그래프로 그려서 이해를 돕고 있는지 확인
        - 잘 작성되었다고 생각되는 부분을 캡쳐해 근거로 첨부합니다.
        - 회고에서 배운점과 아쉬운점, 느낀점, 그리고 문제들의 원인 분석 등을 논리적으로 작성하였습니다.
        - ![image](https://github.com/lys678/Exploration/assets/137245511/bc2d2d4e-7883-45c7-bbd8-28ab922c9898)


        
- [X]  **5. 코드가 간결하고 효율적인가요?**
    - 파이썬 스타일 가이드 (PEP8) 를 준수하였는지 확인
    - 하드코딩을 하지않고 함수화, 모듈화가 가능한 부분은 함수를 만들거나 클래스로 짰는지
    - 코드 중복을 최소화하고 범용적으로 사용할 수 있도록 함수화했는지
        - 잘 작성되었다고 생각되는 부분을 캡쳐해 근거로 첨부합니다.
        - 대부분의 단계에서 함수를 사용하여 범용성을 넓게 작성하였고, class를 활용하여 여러 함수를 효율적으로 사용할 수 있도록 작성하였습니다.
        - ![image](https://github.com/lys678/Exploration/assets/137245511/4d6ca704-90d0-4f77-8f49-855b34e30b6c)
        - ![image](https://github.com/lys678/Exploration/assets/137245511/b25b8d39-5095-4d95-bfd8-046329fa1617)




# 참고 링크 및 코드 개선
```

```
