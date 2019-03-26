# EasySorter
a very powerful utility for sorting a list of elements order by fieds of the element 


## Quickstart

### Clone, build and install
``` bash
git clone https://github.com/tangaiyun/EasySorter.git
cd EasySorter
mvn clean install
```

### Add to your POM
Then create a Spring boot API project refer to sample project "demo1"，and you need to add dependency in pom.xml

``` xml
        <dependency>
            <groupId>com.example</groupId>
            <artifactId>EasySort</artifactId>
            <version>0.0.1-SNAPSHOT</version>
        </dependency>
```

### Usage
please refer to the EasySorterTest.java
``` java
public class EasySorterTest {
	@Data
	@AllArgsConstructor
	static class MyBean {
		private String name;
		private Integer score;
		private Integer index;
	}

	public static void main(String[] args) {
		MyBean a = new MyBean("A", 98, 3);
		MyBean b = new MyBean("B", 67, 5);
		MyBean c = new MyBean("C", null, 4);
		MyBean d = new MyBean("D", 89, 1);
		MyBean e = new MyBean("E", 98, null);
		MyBean f = new MyBean("F", 89, 6);
		MyBean g = new MyBean("G", 98, 3);
		List<MyBean> list = new ArrayList<>();

		list.add(a);
		list.add(b);
		list.add(c);
		list.add(d);
		list.add(e);
		list.add(f);
		list.add(g);
	
		List<MyBean> result = EasySorter.sort(list, "-score,index,-name", false);

		result.forEach(System.out::println);

	}
}
```
