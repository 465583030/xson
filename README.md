xson
====

Java object serialization and de-serialization processor


## 1. ��Ŀ����

Xson��һ��Java�������л��ͷ����л�����֧��Java�����ֽ���������л����ʹ��ֽ����鵽Java����ķ����л���

## 2. ֧�ֵĶ�������

* 1.Java POJO����
* 2.��������:byte,short,int,long,float,double,boolean,char
* 3.��װ����:Byte,Short,Integer,Long,Float,Double,Boolean,Character
* 4.String
* 5.Collection
* 6.Map
* 7.Enum
* 8.TimeZone
* 9.Class
* 10.BigDecimal
* 11.BigInteger
* 12.Class
* 13.StringBuffer
* 14.StringBuilder
* 15.URI
* 16.URL
* 17.UUID	
* 18.Locale
* 19.Currency
* 20.TimeZone
* 21.java.util.Date
* 22.java.sql.Date
* 23.java.sql.Time
* 24.java.sql.Timestamp
* 25.InetAddress
* 26.Inet4Address
* 27.Inet6Address
* 28.InetSocketAddress

## 3. ��maven���������xson����

## 4. ʹ��ʾ��

1.ʹ��xson���ж����ֽ���������л�

	User user = new User();
	//set....
	byte[] data = XSON.write(user);

2.ʹ��xson�����ֽ����鵽����ķ����л�

	//byte[] data = XSON.write(user);
	User user = XSON.parse(data);

## 5. �û���չ

1.��xson������û��Զ����POJO���ͣ�����ʹ�����л��ķ����л�֮ǰ������

	Map<String, String> prop = new HashMap<String, String>();
	prop.put("org.xson.testmodel.XUser7", "x7");
	prop.put("org.xson.testmodel.XUser6", "x6");
	XsonSupport.addCustomAgreementType(prop);

2.�û��Զ���Serializer

	public class CustomerSerializer implements XsonWriter {
	
		@Override
		public void write(Object target, ByteModel model) {
			// Implementation code
		}
	}

3.�û��Զ���Deserializer

	public class CustomerDeserializer implements XsonReader {
		@Override
		public Object read(ReaderModel model) {
			// Implementation code
			return null;
		}
	}

4.��xson������û��Զ����Serializer��Deserializer

	XsonSupport.addCustomSupportType(XUser1.class, new CustomerSerializer(), new CustomerDeserializer());