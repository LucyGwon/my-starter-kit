새 React 컴포넌트 파일을 생성하고 기본 템플릿 코드를 추가합니다.

## 사용법

```
/add-component <ComponentName> [경로]
```

- `ComponentName`: 생성할 컴포넌트 이름 (PascalCase)
- `경로` (선택): 컴포넌트를 생성할 디렉토리 (기본값: `src/components`)

## 동작

1. 사용자가 제공한 `$ARGUMENTS`에서 컴포넌트 이름과 경로를 파싱합니다.
   - 첫 번째 인자: 컴포넌트 이름 (필수)
   - 두 번째 인자: 경로 (선택, 기본값: `src/components`)
2. 지정된 경로에 `<ComponentName>/` 폴더를 생성합니다.
3. 다음 파일들을 생성합니다:
   - `<ComponentName>.tsx` — 컴포넌트 본체
   - `index.ts` — re-export
4. 아래 템플릿을 사용합니다.

### `<ComponentName>.tsx` 템플릿

```tsx
import { FC } from 'react'

interface <ComponentName>Props {
  className?: string
}

const <ComponentName>: FC<<ComponentName>Props> = ({ className }) => {
  return (
    <div className={className}>
      <ComponentName />
    </div>
  )
}

export default <ComponentName>
```

### `index.ts` 템플릿

```ts
export { default } from './<ComponentName>'
```

## 규칙

- 컴포넌트 이름은 반드시 PascalCase여야 합니다. 그렇지 않으면 자동 변환하고 사용자에게 알립니다.
- 이미 동일한 이름의 파일이 존재하면 덮어쓰지 말고 사용자에게 확인을 요청합니다.
- 생성 완료 후 생성된 파일 경로를 출력합니다.
