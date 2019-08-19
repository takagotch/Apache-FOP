### apache-fop
---
https://github.com/apache/fop

https://xmlgraphics.apache.org/fop/

```java
// fop-core/src/test/java/org/apache/fop/render/ps/AbstractPostScriptTest.java

public abstract class AbstractPostScriptTest extends AbstractRenderingTest {
  protected File renderFile(FOUserAgent, ua, String resourceName, String suffix)
      throws Exception {
    return renderFile(ua, resourceName, suffix, MimeConstants.MIME_POSTSCRIPT);  
  }
  
  protected void checkResourceComment(DSCParser parser, String comment, PSResource resource)
      throws IOException, DSCException {
    AbstractResourceDSCComment resComment;
    resComment = (AbstractResourceDSCComment)gotoDSCComment(parser, comment);
    assertEquals(resource, resComment.getResource());
  }
  
  protected static DSCComment gotoDSCComment(DSCParser parser, String name)
      throws IOException, DSCException {
    while (parser.hasNext()) {
      DSCEvent event = parser.nextEvent();
      if (event.isDSComment()) {
        DSCComment comment = event.asDSCComment();
        if (comment.getName().equals(name)) {
          return comment;
        }
      }
    }    
    return null;
  }
}
```

```
```

```
```


