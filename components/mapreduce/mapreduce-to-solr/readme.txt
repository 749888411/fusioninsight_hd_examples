ҵ�񳡾���
һ��mapreduceӦ�ô�HDFS�ж�ȡ���ݣ��������󣬽��������д�뵽solr�����洢��HDFS�С�

ǰ�᣺
1.����һ��ҵ���˺ţ����з���solrָ��collection��Ȩ�ޣ�Ҳ���з���HDFS���ݵ�Ȩ�ޣ������ύӦ�õ�yarn���е�Ȩ�ޣ�ĳ�����У�
2.�������������Ѿ�����ĳ��HDFS·���£����硰/user/tester1/mapreduce/input����
3.��װ��FusionInsight HD�ͻ��ˣ�������YARN��HDFS��Solr�������

�ο���Ӧ�ÿ���ָ�ϡ�->"��ȫģʽ"->"MapReduce����ָ��"->"�������"->"��Linux���������г���"->"���벢���г���"
1.���Ӧ�ó����jar������󣬽�jar������ĳ��·���£����磺/opt/zhuojunjian/jar��jar��ΪmrToSolr-C70.jar��
2.��reduce�׶���֤����������ļ�������user.keytab�ļ���krb5.conf��jaas.conf�����ļ�����ʾ��������Ϊ��jaas_mr.conf�����ȣ�����ĳ��·���£����磺/opt/zhuojunjian/conf��
���У�jaas.conf�����ݣ��ο�ָ���е�ʾ����
3.�ύӦ�ø�yarnʱ��ͨ��kinit�����֤�����磺
kinit -kt /opt/zhuojunjian/conf/user.keytab tester1
4.export�����������Ϣ��ҵ��jar������Ӧ�����������jar�������磺
export YARN_USER_CLASSPATH=/opt/zhuojunjian/conf/:/opt/zhuojunjian/hadoopclient/Solr/lib/*:/opt/zhuojunjian/jar/*
5.�ύӦ�ã�
yarn jar mrToSolr-C70.jar com.huawei.bigdata.mapreduce.examples.MapReduceToSolr /user/tester1/mapreduce/input /user/tester1/mapreduce/output

