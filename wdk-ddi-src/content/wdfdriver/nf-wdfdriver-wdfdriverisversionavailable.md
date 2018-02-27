---
UID: NF:wdfdriver.WdfDriverIsVersionAvailable
title: WdfDriverIsVersionAvailable function
author: windows-driver-content
description: The WdfDriverIsVersionAvailable method returns a Boolean value that indicates whether the driver is running with a specified version of the Kernel-Mode Driver Framework library.
old-location: wdf\wdfdriverisversionavailable.htm
old-project: wdf
ms.assetid: 5635b99d-c58d-4a17-bb51-2dc38e51421a
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: DFDriverObjectRef_56291c91-1c81-486d-89ce-948d037b8bc4.xml, WdfDriverIsVersionAvailable, WdfDriverIsVersionAvailable method, kmdf.wdfdriverisversionavailable, wdf.wdfdriverisversionavailable, wdfdriver/WdfDriverIsVersionAvailable
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfdriver.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.ddi-compliance: DriverCreate, KmdfIrql, KmdfIrql2
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (KMDF); WUDFx02000.dll (UMDF)
req.dll: 
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	Wdf01000.sys
-	Wdf01000.sys.dll
-	WUDFx02000.dll
-	WUDFx02000.dll.dll
apiname:
-	WdfDriverIsVersionAvailable
product: Windows
targetos: Windows
req.typenames: WDF_DRIVER_INIT_FLAGS
req.product: Windows 10 or later.
---

# WdfDriverIsVersionAvailable function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WdfDriverIsVersionAvailable</b> method returns a Boolean value that indicates whether the driver is running with a specified version of the Kernel-Mode Driver Framework library.


## -syntax


````
BOOLEAN WdfDriverIsVersionAvailable(
  _In_ WDFDRIVER                            Driver,
  _In_ PWDF_DRIVER_VERSION_AVAILABLE_PARAMS VersionAvailableParams
);
````


## -parameters




### -param Driver [in]

A handle to the driver's framework driver object that the driver obtained from a previous call to <a href="..\wdfdriver\nf-wdfdriver-wdfdrivercreate.md">WdfDriverCreate</a> or <a href="..\wdfdriver\nf-wdfdriver-wdfgetdriver.md">WdfGetDriver</a>.


### -param VersionAvailableParams [in]

A pointer to a <a href="..\wdfdriver\ns-wdfdriver-_wdf_driver_version_available_params.md">WDF_DRIVER_VERSION_AVAILABLE_PARAMS</a> structure that identifies a version of the framework library.


## -returns



<b>WdfDriverIsVersionAvailable</b> returns <b>TRUE</b> if the driver is running with the version of the library that the <i>VersionAvailableParams</i> parameter specifies. 

The method returns <b>FALSE</b> if the driver is not running with the specified library version or if the WDF_DRIVER_VERSION_AVAILABLE_PARAMS structure is invalid.

A system bug check occurs if the <i>Driver</i> handle is invalid.






## -remarks



For more information about library versions, see <a href="https://msdn.microsoft.com/51db6f3c-45cb-46a7-9dd4-2bab67893fea">Framework Library Versioning</a>.


#### Examples

The following code example reports an error if it detects an unexpected library version number.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>WDF_DRIVER_VERSION_AVAILABLE_PARAMS ver;

WDF_DRIVER_VERSION_AVAILABLE_PARAMS_INIT(&amp;ver, 1, 0);
if (!WdfDriverIsVersionAvailable(
                                 driver,
                                 &amp;ver
                                 )) {
    DbgPrint("Unexpected library version.\n");
}</pre>
</td>
</tr>
</table></span></div>



## -see-also

<a href="..\wdfdriver\nf-wdfdriver-wdfgetdriver.md">WdfGetDriver</a>



<a href="..\wdfdriver\nf-wdfdriver-wdfdriverretrieveversionstring.md">WdfDriverRetrieveVersionString</a>



<a href="..\wdfdriver\ns-wdfdriver-_wdf_driver_version_available_params.md">WDF_DRIVER_VERSION_AVAILABLE_PARAMS</a>



<a href="..\wdfdriver\nf-wdfdriver-wdfdrivercreate.md">WdfDriverCreate</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfDriverIsVersionAvailable method%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

