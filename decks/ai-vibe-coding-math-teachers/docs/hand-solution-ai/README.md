# 손풀이 해설 프로젝트

수학 문제 이미지 또는 PDF를 입력받아, 학생이 따라갈 수 있는 한 장짜리 손풀이 해설 이미지를 만드는 프로젝트이다.

## 먼저 읽을 문서

1. `Agent.md`
2. `docs/context_notes.md`
3. `docs/project_plan.md`
4. `docs/checklist.md`
5. `docs/development_environment_guide.md`
6. `docs/solution_skills/advanced_skill_policy.md`
7. `docs/solution_skills/distance_product.md`

## 여러 장비에서 작업하는 방법

노트북과 로컬 PC를 번갈아 사용할 때는 Git 원격 저장소를 기준으로 작업한다.

현재 GitHub 저장소:

```text
https://github.com/hanhobin1011-cmyk/handwritten-math-solution-ai
```

두 장비의 권장 프로젝트 폴더:

```powershell
C:\Users\<사용자>\Documents\손풀이 해설
```

PC에서 처음 세팅할 때:

```powershell
cd "$env:USERPROFILE\Documents"
git clone https://github.com/hanhobin1011-cmyk/handwritten-math-solution-ai.git "손풀이 해설"
cd "손풀이 해설"
git status
```

처음 세팅할 때는 `.env.example`을 각 장비의 `.env`로 복사한 뒤 필요한 값을 채운다. `.env`는 Git에 올리지 않는다.

작업 시작:

```powershell
git pull
git status
```

작업 종료:

```powershell
git status
git add <변경파일>
git commit -m "작업 내용 요약"
git push
```

자세한 기준은 `docs/development_environment_guide.md`를 따른다.

## 현재 검증 명령

기본 샘플 검증:

```powershell
node tools/validate_artifact.mjs test_problem_001
```

최근 작업 샘플 검증:

```powershell
node tools/validate_artifact.mjs problem_021
```

검증 결과는 `data/validation_reports/`에 저장된다.
