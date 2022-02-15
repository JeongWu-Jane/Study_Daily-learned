## UUID
> 네트워크 상에서 고유성이 보장되는 id를 만들기 위한 표준 규약
- Universally Unique Identifier
- 범용 고유 식별자
- 유일한 식별자 생성할 때 사용
` UUID one = UUID.randomUUID();`


## SecureRandom
> 난수 생성 class
- 난수 생성할떄 예측할수 없는 seed 이용하여 난수 생성
### Random 비교
- 난수 생성할때 seed값으로 '시간' 이용
