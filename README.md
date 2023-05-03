# LearnJavaWicket
    Nó được xây dựng trên máy chủ
    Nó được xây dựng trước khi HTML gửi đến client
    Mã HTML được tạo ra sử dụng mô hình này.
Lý do sử dụng framework :
. Chúng ta ghét code "mỳ" bởi nó rối rắm
. Chúng ta cần dùng các framework để nó chia "business code" ra khỏi "presentation layer"
. Các framework này đã khiến cho MVC pattern trở nên vô cùng hữu dụng và nổi tiếng
Lợi ích sử dụng wicket framework so với other:
.Webpages là objects: Có thể sử dụng thừa kế cho HTML mark up để build ra 1 gui nhất quán cho app
. Không cần lo lắng cho trạng thái của app: pages và components có thể được coi là các đối tượng đầy đủ trạng thái. Chúng là các đối tượng Java và chúng có thể giữ trạng thái bên trong chúng và tham chiếu các đối tượng khác. Chúng ta có thể ngừng lo lắng về việc theo dõi dữ liệu người dùng được lưu trữ bên trong HttpSession và chúng ta có thể bắt đầu quản lý chúng một cách tự nhiên và minh bạch.
. Testing web dễ dàng hơn: bởi vì pages và component là các object nên có thể sử dụng JUnit để test các hành vi và chắc chắn rằng web của chúng ta render ra đúng hình ảnh mà ta cần.
. Wicket là 100% opensource
. Wicket chỉ là JaVa với good old HTML
. với Wicket chúng ta dễ dàng sử dụng JAvaBeans và POJO.

package org.wicketTutorial;

import org.apache.wicket.request.mapper.parameter.PageParameters;
import org.apache.wicket.markup.html.basic.Label;
import org.apache.wicket.markup.html.WebPage;

public class HomePage extends WebPage {
    public HomePage() {
	   add(new Label("helloMessage", "Hello WicketWorld!"));
    }
}

 Method add(Component component) is inherited from ancestor class org.apache.wicket.MarkupContainer and is used to add children components to a web page.
 Class org.apache.wicket.markup.html.basic.Label is the simplest component shipped with Wicket. It just inserts a string (the second argument of its constructor) inside the corresponding HTML tag.
 

Here is the HTML markup for HomePage (file HomePage.html):

<!DOCTYPE html>
<html>
	<head>
		<meta charset="utf-8" />
		<title>Apache Wicket HelloWorld</title>
	</head>
	<body>

		<div wicket:id="helloMessage">
		[Label's message goes here]
		</div>
	</body>
</html>

public class HomePage extends WebPage {
	public HomePage(){
		add(new Link<Void>("id"){
			@Override
			public void onClick() {
                         //we redirect browser to another page.
                         setResponsePage(AnotherPage.class);
			}
		});
	}
}
