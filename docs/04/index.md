# サーブレットの基本

## サーブレットとは

Tomcatを使って、JavaでHTTPのリクエストを受け付けるためには、Servletは最初に作ったようにEclipseの機能から作るのが簡単です。

Eclipseで最初に作った`hello`プロジェクトを使って作ります。最初の手順をもう一度確認します。

### Servletの作成方法

今回はパッケージは`hello`、クラス名は`FirstServlet`としてください。

- Servletを作りたいプロジェクトを展開し、中にある「src/main/java」を右クリックし、「New」>「Servlet」を選びます。
- 出てきたダイアログで、「package」と、「Class name」入力し、「Next」を押します。Servletでは**必ず**パッケージを宣言するようにしてください。
- 入力後、++"Finish"++を押します。
- ここまでで、Servletが作成されますが、importが古いままなのでどこか編集（スペースを入れて消す）して保存するか、++ctrl+shift+o++（インポートの編成）を押してください。

今回作ったソースは次のようになります。

```java
package hello;

import java.io.IOException;

import jakarta.servlet.ServletException;
import jakarta.servlet.annotation.WebServlet;
import jakarta.servlet.http.HttpServlet;
import jakarta.servlet.http.HttpServletRequest;
import jakarta.servlet.http.HttpServletResponse;

/**
 * Servlet implementation class FirstServlet
 */
@WebServlet("/FirstServlet")
public class FirstServlet extends HttpServlet {
    private static final long serialVersionUID = 1L;

    /**
     * Default constructor.
     */
    public FirstServlet() {
        // TODO Auto-generated constructor stub
    }

    /**
     * @see HttpServlet#doGet(HttpServletRequest request, HttpServletResponse
     *      response)
     */
    protected void doGet(HttpServletRequest request, HttpServletResponse response)
            throws ServletException, IOException {
        // TODO Auto-generated method stub
        response.getWriter().append("Served at: ").append(request.getContextPath());
    }

    /**
     * @see HttpServlet#doPost(HttpServletRequest request, HttpServletResponse
     *      response)
     */
    protected void doPost(HttpServletRequest request, HttpServletResponse response)
            throws ServletException, IOException {
        // TODO Auto-generated method stub
        doGet(request, response);
    }

}
```

コメントや、コンストラクタは不要です。また、`doGet`、`doPost`メソッドに実装がされています（`doGet`、`doPost`の`{}`の間）がこちらも不要です。

余計なものを消したものが、次の内容です。

```java
package hello;

import java.io.IOException;

import jakarta.servlet.ServletException;
import jakarta.servlet.annotation.WebServlet;
import jakarta.servlet.http.HttpServlet;
import jakarta.servlet.http.HttpServletRequest;
import jakarta.servlet.http.HttpServletResponse;

@WebServlet("/FirstServlet")
public class FirstServlet extends HttpServlet {
    private static final long serialVersionUID = 1L;

    protected void doGet(HttpServletRequest request, HttpServletResponse response)
            throws ServletException, IOException {
    }

    protected void doPost(HttpServletRequest request, HttpServletResponse response)
            throws ServletException, IOException {
    }
}
```
