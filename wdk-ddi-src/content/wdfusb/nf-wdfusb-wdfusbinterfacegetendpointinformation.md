---
UID: NF:wdfusb.WdfUsbInterfaceGetEndpointInformation
title: WdfUsbInterfaceGetEndpointInformation function
author: windows-driver-content
description: The WdfUsbInterfaceGetEndpointInformation method retrieves information about a specified USB device endpoint and its associated pipe.
old-location: wdf\wdfusbinterfacegetendpointinformation.htm
old-project: wdf
ms.assetid: c9e204db-f8fc-42e7-9a1b-f08099147ce7
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: ",  , DFUsbRef_fff1d755-32af-48d1-b9d6-faa8b118fa8d.xml, E, G, I, U, W, WdfUsbInterfaceGetEndpointInformation, WdfUsbInterfaceGetEndpointInformation method, a, b, c, d, e, f, i, kmdf.wdfusbinterfacegetendpointinformation, m, n, o, p, r, s, t, wdf.wdfusbinterfacegetendpointinformation, wdfusb/WdfUsbInterfaceGetEndpointInformation"
ms.prod: windows-hardware
ms.technology: windows-devices
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
-	WdfUsbInterfaceGetEndpointInformation
product: Windows
targetos: Windows
req.typenames: WDF_USB_REQUEST_TYPE, *PWDF_USB_REQUEST_TYPE
req.product: Windows 10 or later.
---

# WdfUsbInterfaceGetEndpointInformation function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WdfUsbInterfaceGetEndpointInformation</b> method retrieves information about a specified USB device endpoint and its associated pipe.


## -syntax


````
VOID WdfUsbInterfaceGetEndpointInformation(
  _In_  WDFUSBINTERFACE           UsbInterface,
  _In_  UCHAR                     SettingIndex,
  _In_  UCHAR                     EndpointIndex,
  _Out_ PWDF_USB_PIPE_INFORMATION EndpointInfo
);
````


## -parameters




### -param UsbInterface [in]

A handle to a USB interface object that was obtained by calling <a href="..\wdfusb\nf-wdfusb-wdfusbtargetdevicegetinterface.md">WdfUsbTargetDeviceGetInterface</a>. 


### -param SettingIndex [in]

An index value that identifies an alternate setting for the interface. For more information about alternate settings, see the USB specification.


### -param EndpointIndex [in]

An index value that identifies an endpoint that is associated with the specified alternate setting of the specified interface. (This index value is not the endpoint address.)


### -param EndpointInfo [out]

A pointer to a caller-allocated <a href="..\wdfusb\ns-wdfusb-_wdf_usb_pipe_information.md">WDF_USB_PIPE_INFORMATION</a> structure that the framework fills in.


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

<a href="..\wdfusb\nf-wdfusb-wdfusbtargetdevicegetinterface.md">WdfUsbTargetDeviceGetInterface</a>



<a href="..\wdfusb\nf-wdfusb-wdfusbinterfacegetnumendpoints.md">WdfUsbInterfaceGetNumEndpoints</a>



<a href="..\wdfusb\ns-wdfusb-_wdf_usb_pipe_information.md">WDF_USB_PIPE_INFORMATION</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfUsbInterfaceGetEndpointInformation method%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

