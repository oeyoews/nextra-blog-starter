当您使用一个链接（标签）将用户从您的站点带到另一个站点时，为了保护您的站点安全，应该在链接中添加 rel="noreferrer" 属性。

这个属性指示浏览器不要向其他站点提供任何更多的信息（即 referrer 信息），例如从哪里来的访问者和他们在您的站点上做了什么。这可防止其他站点通过 referrer 信息了解您的站点的敏感信息。

下面是一个可能的链接示例，演示了如何添加 rel="noreferrer" 属性：

<a href="https://www.example.com" target="_blank" rel="noreferrer">
	Example Website
	</a>

在这个示例中，我们为 href 属性设置了一个外部链接地址，并在 target 属性中使用了 "_blank" 以在新标签页中打开该链接。同时，我们还为 rel 属性添加了 "noreferrer" 值来指示浏览器禁用 referrer 信息传递。

需要注意的是，除非您有特殊原因需要传递 referrer 信息，否则最好一直使用 rel="noreferrer" 属性来确保您的站点安全。