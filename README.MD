����Ч����

![github](https://github.com/234687552/ProjectSchedule/blob/master/screenshots/result.gif "github")

ѧϰ�ĵã�
=====
1.�����������Adpter�����getView����ֱ��ʹ��return newItemView��context���Ļ���

	@Override
        public View getView(int position, View convertView, ViewGroup parent) {
            return new ItemView(mContext);
        }
        
�ᵼ���������⣺
	Item�Ļ�����ListView���¹������ʧЧ
ԭ�������ͨ����getVIew����log��

	Log.w("getView", position+","+view );
	
����֪��������ItemVIewǰ��ĵ�ַ�ǲ�һ�µģ���null���***���������ǵ���ԭ��
���������
	��return֮ǰ���ж��Ƿ�Ϊnull��Ȼ��Ϊnull�Ļ���ʵ����һ��view����
	
	@Override
        public View getView(int position, View convertView, ViewGroup parent) {
            ItemView view= (ItemView) convertView;
            if (view==null){
                view=new ItemView(mContext);
            }
            Log.w("getView", position+","+view );
            return view;
        }
        

2.֮ǰ����¼�������ItemView�����ģ�������ItemView�����OnTouch�����������÷���ֵtrue��Ҳ�͵���ListView �����OnTouch������Ч�����Ե����޷�ʵ�ֱ�ֻ֤��һ��չ������Ϊÿһ��Item��Զ��Ƕ����ģ��޷����Ʊ��Item�Զ��ر�չ��
�������ڿ���ֱ����ListVIew�����OnTouch����ʵ��Item����Ч��

3.OnTouchEvent�������⣺
![github](https://github.com/234687552/ProjectSchedule/blob/master/screenshots/onTouchEvent.png "github")