# Update

프레임마다 한번씩 호출, 프레임에 따라 호출되기 때문에 시간이 일정하지 않음
프레임마다 반복되므로 과하게 사용하면 성능이 저하될 수 있음

# FixedUpdate

Update와 달리 프레임마다 호출되는게 아니라 Fixed Timestep에 설정된 값에 따라서 호출
일정하기 때문에 물리효과에 많이 사용 한다

### Fixed Timestep 접근하는법

Edit ➡️ ProjectSettings.. ➡️ Time

# LateUpdate

Update가 호출된 후에 호출
카메라에 많이 사용(Update에서 플레이어가 이동하는 경우가 많기 때문에)