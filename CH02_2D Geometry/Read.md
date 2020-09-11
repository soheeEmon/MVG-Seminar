카메라로 영상을 촬영했을 때 실제 3차원 공간의 좌표계, 카메라 좌표계, 영상 평면, 객체의 3차원 좌표계가 모두 다른데 이 사이의 관계를 정의하기 위해서 (Geometry) 기하학을 사용하게 됩니다. 이때 실제 3차원의 한 점(x, y, z)이 이미지 평면 상에 2차원 점으로(x, y) 투영 변환 (projective transform)이 되기 때문에 우리는 특히 사영 기하학 (projective geometry)를 공부해야 합니다.

유클리디안 공간에서 직교 좌표계를 사용하듯이 사영 기하학에서는 동차좌표를 사용하는 것이 편리합니다. 동차좌표는 2차원 평면상의 점을 3차원 공간 상의 직선에 사상(mapping) 시킨 것으로 평면에서의 한 점을 2개의 좌표가 아닌 3개의 좌표를 사용하여 표현합니다. 일반적으로 n차원의 사영 공간을 n+1개의 좌표로 나타낸다고 할 수 있습니다.
동차 좌표계는 직교 좌표계에서 0이 아닌 실수 w를 x, y에 곱한 후 마지막에 w로 요소를 하나 더 추가하는 것으로 표현합니다. (x, y)에 대한 동차 좌표 표현은 3차원의 한 직선 상에 무한히 존재합니다. 또, 동차좌표의 마지막 요소(argument) w를 scale factor로 사용하여 벡터와 점을 구별할 수 있습니다. 
동차 좌표계에서 0이 아닌 w로 나누어주고 마지막 argument를 제거하면 직교 좌표계를 구할 수 있습니다. 다시 말해 동차 좌표계를 직교 좌표계로 변환하는 것은 w의 scale과 상관없이 동차좌표계 위의 한 직선에 있는 모든 점들을 w=1인 평면의 한 점으로 mapping 된다는 것입니다.

동차좌표를 사용함으로써 얻는 이점은 다음과 같습니다.
유클리디안 공간에서 평행선은 절대 교차하지 않지만 원근감이 적용되는 사영 공간에서는(각도, 길이, 평행성 보존x) 하나의 소실점에서 서로 만나게 됩니다. 이 소실점은 무한대 거리에 존재하는 무한 원점(point at infinity, ideal point)이기 때문에 이를 유클리디안 공간의 직교 좌표계에서 무한대를 표현할 수 없습니다. 따라서 무한대를 유한 좌표로 표현이 가능한 동차 좌표계를 사용하게 되는 것입니다. 점 (x, y)를 1/w를 곱한 동차좌표로 변환하면 (x/w, y/w, 1/w)이 됩니다. w가 0이 되면 (x/w, y/w)는 무한대로 이동하게 됩니다. 그러므로 동차좌표 (x, y, 0)은 (x, y) 방향으로의 무한대의 점이라고 할 수 있습니다.
동차좌표의 또 다른 이점은 위치 변환(affine)이나 투영 변환은 단순한 선형 변환이 아니기 때문에 행렬 연산하기가 어렵습니다. 하지만 동차좌표를 사용하게 되면 이를 결합한 변환까지 단일 행렬로 표현할 수 있습니다.
 
아까 w의 크기와 상관없이 (x, y)에 대한 동차좌표 표현은 3차원 공간 상의 한 직선 위에 존재하는 점들로 표현이 가능하다 했는데 이를 equivalence relation 동치 관계라고 할 수 있습니다.