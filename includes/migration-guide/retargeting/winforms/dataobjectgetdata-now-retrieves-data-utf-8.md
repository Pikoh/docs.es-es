### <a name="dataobjectgetdata-now-retrieves-data-as-utf-8"></a><span data-ttu-id="ffffd-101">DataObject.GetData ahora recupera los datos como UTF-8</span><span class="sxs-lookup"><span data-stu-id="ffffd-101">DataObject.GetData now retrieves data as UTF-8</span></span>

|   |   |
|---|---|
|<span data-ttu-id="ffffd-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="ffffd-102">Details</span></span>|<span data-ttu-id="ffffd-103">Para las aplicaciones que tienen como destino .NET Framework 4 o que se ejecutan en .NET Framework 4.5.1 o versiones anteriores, <code>DataObject.GetData</code> recupera los datos con formato HTML como una cadena ASCII.</span><span class="sxs-lookup"><span data-stu-id="ffffd-103">For apps that target the .NET Framework 4 or that run on the .NET Framework 4.5.1 or earlier versions, <code>DataObject.GetData</code> retrieves HTML-formatted data as an ASCII string.</span></span> <span data-ttu-id="ffffd-104">Como resultado, los caracteres que no son ASCII (los caracteres cuyos códigos ASCII son mayores que 0x7F) se representan mediante dos caracteres aleatorios. Para las aplicaciones que tienen como destino .NET Framework 4.5 o una versión posterior y se ejecutan en .NET Framework 4.5.2, <code>DataObject.GetData</code> recupera los datos con formato HTML como UTF-8, que representa correctamente los caracteres mayores que 0x7F.</span><span class="sxs-lookup"><span data-stu-id="ffffd-104">As a result, non-ASCII characters (characters whose ASCII codes are greater than 0x7F) are represented by two random characters.For apps that target the .NET Framework 4.5 or later and run on the .NET Framework 4.5.2, <code>DataObject.GetData</code> retrieves HTML-formatted data as UTF-8, which represents characters greater than 0x7F correctly.</span></span>|
|<span data-ttu-id="ffffd-105">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="ffffd-105">Suggestion</span></span>|<span data-ttu-id="ffffd-106">Si implementó una solución alternativa para el problema de codificación mediante cadenas con formato HTML (por ejemplo, mediante la codificación explícita de la cadena HTML recuperada del Portapapeles y su transferencia a <xref:System.Text.UTF8Encoding.GetString(System.Byte[],System.Int32,System.Int32)?displayProperty=name>) y va a redestinar la aplicación de la versión 4 a la versión 4.5, esa solución alternativa se debe eliminar. Si por algún motivo se necesita el comportamiento anterior, la aplicación se puede destinar a .NET Framework 4.0 para obtenerlo.</span><span class="sxs-lookup"><span data-stu-id="ffffd-106">If you implemented a workaround for the encoding problem with HTML-formatted strings (for example, by explicitly encoding the HTML string retrieved from the Clipboard by passing it to <xref:System.Text.UTF8Encoding.GetString(System.Byte[],System.Int32,System.Int32)?displayProperty=name>) and you're retargeting your app from version 4 to 4.5, that workaround should be removed.If the old behavior is needed for some reason, the app can target the .NET Framework 4.0 to get that behavior.</span></span>|
|<span data-ttu-id="ffffd-107">Ámbito</span><span class="sxs-lookup"><span data-stu-id="ffffd-107">Scope</span></span>|<span data-ttu-id="ffffd-108">Borde</span><span class="sxs-lookup"><span data-stu-id="ffffd-108">Edge</span></span>|
|<span data-ttu-id="ffffd-109">Versión</span><span class="sxs-lookup"><span data-stu-id="ffffd-109">Version</span></span>|<span data-ttu-id="ffffd-110">4.5.2</span><span class="sxs-lookup"><span data-stu-id="ffffd-110">4.5.2</span></span>|
|<span data-ttu-id="ffffd-111">Tipo</span><span class="sxs-lookup"><span data-stu-id="ffffd-111">Type</span></span>|<span data-ttu-id="ffffd-112">Redestinación</span><span class="sxs-lookup"><span data-stu-id="ffffd-112">Retargeting</span></span>|
|<span data-ttu-id="ffffd-113">API afectadas</span><span class="sxs-lookup"><span data-stu-id="ffffd-113">Affected APIs</span></span>|<ul><li><xref:System.Windows.DataObject.GetData(System.String)?displayProperty=nameWithType></li><li><xref:System.Windows.DataObject.GetData(System.Type)?displayProperty=nameWithType></li><li><xref:System.Windows.DataObject.GetData(System.String,System.Boolean)?displayProperty=nameWithType></li></ul>|
