---
UID: NF:wdfwmi.WdfWmiInstanceDeregister
title: WdfWmiInstanceDeregister function
author: windows-driver-content
description: The WdfWmiInstanceDeregister method deregisters a specified instance of a WMI data provider from the system's WMI service.
old-location: wdf\wdfwmiinstancederegister.htm
old-project: wdf
ms.assetid: 2167504e-ca92-4427-9101-04a2c2bf66df
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: PFN_WDFWMIINSTANCEDEREGISTER, DFWMIRef_4e04e7da-3a14-4bd4-a430-8f5f3624b61a.xml, kmdf.wdfwmiinstancederegister, WdfWmiInstanceDeregister, WdfWmiInstanceDeregister method, wdf.wdfwmiinstancederegister, wdfwmi/WdfWmiInstanceDeregister
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfwmi.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 
req.ddi-compliance: DriverCreate, KmdfIrql, KmdfIrql2
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (see Framework Library Versioning.)
req.dll: 
req.irql: "<=DISPATCH_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	Wdf01000.sys
-	Wdf01000.sys.dll
apiname:
-	WdfWmiInstanceDeregister
product: Windows
targetos: Windows
req.typenames: WDF_WMI_PROVIDER_FLAGS
req.product: Windows 10 or later.
---

# WdfWmiInstanceDeregister function


## -description


<p class="CCE_Message">[Applies to KMDF only]

The <b>WdfWmiInstanceDeregister</b> method deregisters a specified instance of a WMI data provider from the system's WMI service.


## -syntax


````
VOID WdfWmiInstanceDeregister(
  _In_ WDFWMIINSTANCE WmiInstance
);
````


## -parameters




### -param WmiInstance [in]

A handle to a WMI instance object that the driver obtained from a previous call to <a href="..\wdfwmi\nf-wdfwmi-wdfwmiinstancecreate.md">WdfWmiInstanceCreate</a>.


## -returns



None.

A bug check occurs if the driver supplies an invalid object handle.






## -remarks



For more information about the <b>WdfWmiInstanceDeregister</b> method, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/initializing-wmi-support-in-your-driver">Registering Provider Instances</a>. For more information about WMI, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/supporting-wmi-in-kmdf-drivers">Supporting WMI in Framework-Based Drivers</a>.


<a href="..\wdfwmi\nf-wdfwmi-wdfwmiinstanceregister.md">WdfWmiInstanceRegister</a> deregisters the provider instance synchronously (that is, before returning) if it is called at IRQL = PASSIVE_LEVEL and asynchronously if it is called at IRQL &gt; PASSIVE_LEVEL. 


#### Examples

The following code example deregisters a specified instance of a WMI data provider from the system's WMI service.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>WdfWmiInstanceDeregister(wmiInstance);</pre>
</td>
</tr>
</table></span></div>



## -see-also

<a href="..\wdfwmi\nf-wdfwmi-wdfwmiinstancecreate.md">WdfWmiInstanceCreate</a>



<a href="..\wdfwmi\nf-wdfwmi-wdfwmiinstanceregister.md">WdfWmiInstanceRegister</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfWmiInstanceDeregister method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

