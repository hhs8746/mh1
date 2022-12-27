# mh1
import numpy as np
import matplotlib.pyplot as plt
# 백색소음 구현하기 
# 표준 정규분포를 따르는 1000개의 난수를 생성한다
x = np.random.normal(0, 1, 1000)

plt.plot(x, linestyle='-')

## 0에 중심선 그리기
plt.axhline(0, 0, 200, color='red', linestyle='--', linewidth=2)
plt.show()


#확률 보행과정 구현하기
# 위와 아래로 움직일 확률이 0.5로 같다
p=0.5 
  
# 0에서 시작한다
start = 0
rand_walks = [start]

# 0에서 1사이의 난수를 500개 발생시킨다
t = np.random.random(500)
down = t < p
up = t >= p

# 확률보행 프로세스
# z(t) = z(t-1) + a(t) 
for d, u in zip(down, up):
    rand_walks.append(rand_walks[-1] - d + u)

# 그래프로 나타내기
plt.plot(rand_walks)
plt.show()
