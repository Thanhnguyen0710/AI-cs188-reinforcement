# AI-cs188-reinforcement
Câu 1
Em viết thêm trong hàm init duyệt iterations, duyệt các state trong mdp trong các state thì duyệt các 
action cập nhật v và lấy v max trong các action cập nhật vào newvalues sau khi duyệt hết
các state thì cập nhật vào self.values

computeQValueFromValues: tạo biến actionvalue để lưu kết quả duyệt các nextState và 
prop của state và action, sau đó tính tổng theo ct tính Q_values và trả về actionvalue

computeActionFromValues: lấy bessAction từ mdp.getPossibleActions
khởi tạo maxvalue là âm vô cùng duyệt các action tính Q_value nếu Q_value > maxValue
thì cập nhật maxValue và bestAction. Sẽ trả về bestAction

Câu 2
Em sẽ giảm answerNoise = 0 
giữ nguyên answerDiscount

Câu 3 
a)
    answerDiscount = 0.9
    answerNoise = 0
    answerLivingReward = -5

b)
    answerDiscount = 0.3
    answerNoise = 0.1
    answerLivingReward = 0
c)
    answerDiscount = 0.9
    answerNoise = 0
    answerLivingReward = -2
d)
    answerDiscount = 0.9
    answerNoise = 0.3
    answerLivingReward = 0
e)
    answerDiscount = 0.9
    answerNoise = 0
    answerLivingReward = 999999
Câu 4
getQValue: sẽ trả về self.q_values[(state, action)]

computeValueFromQValues:
Khởi tạo legalActions = self.getLegalActions(state)
Nếu len(legalAction) là 0 thì sẽ trả về 0.0
Duyệt các action và cập nhật getQvalue sẽ trả về tmp[tmp.argMax()] 

computeActionFromQValues: 
Lấy  các actions từ self.getLegalActions(state)
Khởi tạo max_val là âm vô vùng
duyệt các action tính q_value của action đó nếu qvalue > max thì cập nhật max_val và best_action
Khi duyệt xong thì sẽ trả về best_action

update:
Khởi tạo old_q_value bằng self.getQValue(state, action)
Khởi tạo lod_part bằng (1 - self.alpha) * old_q_value
Khởi tạo reward_part bằng self.alpha * reward
Nếu không có nextState thì sẽ cập nhật self.q_values = old_part + reward_part
Nếu có thì sẽ tính nextState_part là self.alpha * self.discount * self.getValue(nextState) và
sẽ cập nhật self.q_values[(state, action)] = old_part + reward_part + nextState_part

Câu 5
getAction:
Khởi tạo legal_action là self.getLegalActions(state)
Khởi tạo explore là util.flipCoin(self.epsilon)
nếu explore là true thì sẽ trả về 1 số random từ legal_action
nếu explore là false thì trả về self.getPolicy(state)

Câu 6
trả về NOT POSSIBLE

Câu 8 
getQValue:
Khởi tạo features lấy các từ self.featExtractor.getFeatures(state, action)
sẽ trả về tông các features và weights của nó

update:
khởi tạo diff theo công thức
khởi tạo features lấy các từ self.featExtractor.getFeatures(state, action)
và cập nhật từng weights lần lượt theo features theo công thức























