# VS CODE 에서 Python 코딩 컨벤션 설정하기

- 참고 사이트: https://jhyeok.com/python-with-vscode/

- Window 기준으로 작성하였으므로 다른 OS에서는 조금 다를 수 있습니다.

## 1. 가상 환경 구성

- pip를 사용하면 global하게 설치 되므로 모든 프로젝트에 영향을 줍니다.

- 그러므로 대도록 독립된 가상환경을 만들어 해당 프로젝트에만 적용 되도록 해줍니다.

- pip를 사용하여 pipenv를 설치합니다

  - ```cmd
    pip install pipenv
    ```

- 버전 확인

  - ```cmd
    pipenv --version
    ```

  - ```cmd
    pipenv, version 2020.6.2
    ```
    - 버전은 다를 수 있습니다.

- 가상 환경 들어가기

  - ```cmd
    pipenv shell
    ```
    
    - Pipfile이 생성됩니다.

    - 가상환경에서 나오고 싶으면 터미널에 exit를 치면 됩니다.

> 이미 있는 가상 환경을 적용하고 싶다면 터미널에서 해당 가상환경 폴더의 Scripts폴더로 이동 후 activate를 치면 가상환경으로 들어가는데 그 곳에서 에디터를 열어 작업하면 됩니다.

- 가상 환경 위치 확인

  - ```cmd
    pipenv --venv
    ```

- 패키지 설치

  - Pipfile.lock파일에서 관리합니다.

  - ```cmd
    pipenv install [패키지명]
    ```

- 개발용 패키지 설치

  - ```cmd
    pipenv install [패키지명] --dev
    ```

- Pipfile.lock에 있는 패키지 한 번에 설치

  - ```cmd
    pipenv install
    ```

- Pipfile.lock에 있는 개발용 패키지 한 번에 설치

  - ```cmd
    pipenv install --dev
    ```

## 2. Black

- 파이썬 커뮤니티에서 가장 널리 쓰이고 있는 코드 포멧터입니다.

- Ctrl + Shift + p를 이용해서 settings.json을 열어줍니다.

- 옵션을 추가해 줍니다.

  - ```json
    {
      "python.formatting.provider": "black",
      "python.formatting.blackArgs": [
        "--line-length",
        "100"
      ],
      "editor.formatOnSave": true
    }
    ```

    - "python.formatting.provider": "black",
      
      - black을 사용하겠다는 옵션입니다.

    - "editor.formatOnSave": true

      - 저장시에 자동으로 format을 적용한다는 옵션입니다.

## 3. Pylint

- 패키지를 설치해 줍니다

  - ```cmd
    pipenv install pylint
    ```

    - pip로 설치해도 상관없습니다.

- Ctrl + Shift + p 에서 PythonL Select Linter클릭 후 pylint를 클릭 합니다.

- settings.json

  ```json
  "python.linting.pylintEnabled": true,
  "python.linting.enabled": true
  ```

- 추가 되었다면 성공입니다.