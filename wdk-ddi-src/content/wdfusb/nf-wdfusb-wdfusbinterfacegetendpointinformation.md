---
UID: NF:wdfusb.WdfUsbInterfaceGetEndpointInformation
title: WdfUsbInterfaceGetEndpointInformation function
description: The WdfUsbInterfaceGetEndpointInformation method retrieves information about a specified USB device endpoint and its associated pipe.
old-location: wdf\wdfusbinterfacegetendpointinformation.htm
tech.root: wdf
ms.assetid: c9e204db-f8fc-42e7-9a1b-f08099147ce7
ms.date: 02/26/2018
ms.keywords: DFUsbRef_fff1d755-32af-48d1-b9d6-faa8b118fa8d.xml, WdfUsbInterfaceGetEndpointInformation, WdfUsbInterfaceGetEndpointInformation method, kmdf.wdfusbinterfacegetendpointinformation, wdf.wdfusbinterfacegetendpointinformation, wdfusb/WdfUsbInterfaceGetEndpointInformation
ms.topic: function
req.header: wdfusb.h
req.include-header: Wdfusb.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.ddi-compliance: DriverCreate, KmdfIrql, KmdfIrql2, UsbKmdfIrql, UsbKmdfIrql2
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (KMDF); WUDFx02000.dll (UMDF)
req.dll: 
req.irql: "<=DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Wdf01000.sys
-	Wdf01000.sys.dll
-	WUDFx02000.dll
-	WUDFx02000.dll.dll
api_name:
-	WdfUsbInterfaceGetEndpointInformation
product:
- Windows
targetos: Windows
req.typenames: 
---

# WdfUsbInterfaceGetEndpointInformation function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

The <b>WdfUsbInterfaceGetEndpointInformation</b> method retrieves information about a specified USB device endpoint and its associated pipe.


## -parameters




### -param UsbInterface [in]

A handle to a USB interface object that was obtained by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff550092">WdfUsbTargetDeviceGetInterface</a>. 


### -param SettingIndex [in]

An index value that identifies an alternate setting for the interface. For more information about alternate settings, see the USB specification.


### -param EndpointIndex [in]

An index value that identifies an endpoint that is associated with the specified alternate setting of the specified interface. (This index value is not the endpoint address.)


### -param EndpointInfo [out]

A pointer to a caller-allocated <a href="https://msdn.microsoft.com/library/windows/hardware/ff553037">WDF_USB_PIPE_INFORMATION</a> structure that the framework fills in.


## -returns



None.

A bug check occurs if the driver supplies an invalid object handle.






## -remarks



For more information about the <b>WdfUsbInterfaceGetEndpointInformation</b> method and USB I/O targets, see <a href="https://msdn.microsoft.com/195c0f4b-7f33-428a-8de7-32643ad854c6">USB I/O Targets</a>.


#### Examples

The following code example obtains the number of endpoints that a USB interface supports and then calls <b>WdfUsbInterfaceGetEndpointInformation</b> for each endpoint.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>WDF_USB_PIPE_INFORMATION endPointInfo;
BYTE settingIndex, i;

settingIndex = 0;
numEndpoints = WdfUsbInterfaceGetNumEndpoints(
                                          UsbInterface,
                                          settingIndex
                                          );

for (i = 0; i &lt; numEndpoints; i++){
    WDF_USB_PIPE_INFORMATION_INIT(&amp;endPointInfo);
    WdfUsbInterfaceGetEndpointInformation(
                                          UsbInterface,
                                          settingIndex,
                                          i,
                                          &amp;endPointInfo
                                          );

    //
    // Examine endpoint information here.
    //
...
}</pre>
</td>
</tr>
</table></span></div>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff553037">WDF_USB_PIPE_INFORMATION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550068">WdfUsbInterfaceGetNumEndpoints</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550092">WdfUsbTargetDeviceGetInterface</a>
 

 

