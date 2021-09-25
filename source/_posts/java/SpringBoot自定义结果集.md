使用java泛型定义

```java
public class Result<T> {
    private String code;
    private String message;
    private boolean success;
    private T result;

    public static Result success(){
        return success(null);
    }

    public static Result success(Object o){
        Result result=new Result();
        result.setCode("200");
        result.setMessage("成功");
        result.setSuccess(true);
        result.setResult(o);
        return result;
    }

    public static Result error(String code, String message){
        Result result=new Result();
        result.setCode(code);
        result.setMessage(message);
        result.setSuccess(false);
        result.setResult(null);
        return result;
    }

    public static Result error(String message){
        Result result=new Result();
        result.setCode("-1");
        result.setMessage(message);
        result.setSuccess(false);
        result.setResult(null);
        return result;
    }

    public String getCode() {
        return code;
    }

    public void setCode(String code) {
        this.code = code;
    }

    public String getMessage() {
        return message;
    }

    public void setMessage(String message) {
        this.message = message;
    }

    public boolean isSuccess() {
        return success;
    }

    public void setSuccess(boolean success) {
        this.success = success;
    }

    public T getResult() {
        return result;
    }

    public void setResult(T result) {
        this.result = result;
    }

    @Override
    public String toString() {
        return "Result{" +
                "code='" + code + '\'' +
                ", message='" + message + '\'' +
                ", success=" + success +
                ", result=" + result +
                '}';
    }
}
```

