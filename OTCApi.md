#B���̻��µ�API�ĵ�
Ŀǰ������B���̻��µ�api�������ǽ��ṩB���̻�accessKey����Ҫʹ�������ṩ��accessKey������ӿ���ص��������Ķ������ı���
#�ӿ�˵��
- ǩ��˵���������ǩ������sha256������ӿڵ�url���������key��ʱ���(���뼶-������13λ��)���м��ܵõ����ģ�Ȼ���������н����ĸ���sign�����ӽ�����ͷ� ���磺get����api/Pay ������symbol��openid��remark������Ҫ�� api/Pay?accessKey=****&symbolId=1001&orderBuyType=2&value=100&payId=1&timestamp=1567412503000 ����sha256���ܣ�ע������������ǰ��ռ�������������ģ�Ȼ��������ͷ�����sign������ֵ���ǵõ�������
- ֻҪ�����������ӿ�ͳһ����200״̬�룬���ص�Json��ʽΪ ?
{
  "success": true,
  "data": "string"
}

###�ӿ��б�

|�ӿڷ���|����|˵��|
| --------   | -----:  | :----:  |
|tripleotc/ad/OrderVerify|post|B���̻��µ�|

tripleotc/ad/OrderVerify B���̻��µ�

###�������
|��������|�Ƿ����|����|����|Ĭ��ֵ|ȡֵ��Χ|
| --------   | -----:  | :----:  |
|symbolId|true|int|����Id|��|1011(usdt)|
|orderBuyType|true|int|������|��|1--���������|
|value|true|decimal|��ֵ|��||
|payId|true|int|֧����ʽ|��|1-֧������2-΢�ţ�3-����|

###���ز���
|��������|�Ƿ����|����|����|Ĭ��ֵ|ȡֵ��Χ|
| --------   | -----:  | :----:  |
|success|true|bool|�����Ƿ�ɹ�|true|true��false|
|data|true|json|	���ɹ��򷵻ص�ַ�����򷵻ش�����Ϣ||||