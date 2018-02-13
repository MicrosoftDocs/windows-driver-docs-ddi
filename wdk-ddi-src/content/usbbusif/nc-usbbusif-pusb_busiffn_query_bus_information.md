---
UID: NC:usbbusif.PUSB_BUSIFFN_QUERY_BUS_INFORMATION
title: PUSB_BUSIFFN_QUERY_BUS_INFORMATION
author: windows-driver-content
description: The QueryBusInformation routine gets information about the bus.
old-location: buses\querybusinformation.htm
old-project: usbref
ms.assetid: cc03ae88-89ba-44ff-bfe7-6255f2a2ec5c
ms.author: windowsdriverdev
ms.date: 2/8/2018
ms.keywords: buses.querybusinformation, QueryBusInformation, PUSB_BUSIFFN_QUERY_BUS_INFORMATION, QueryBusInformation callback function [Buses], QueryBusInformation, USB_BUSIFFN_QUERY_BUS_INFORMATION, USB_BUSIFFN_QUERY_BUS_INFORMATION, usbbusif/QueryBusInformation, usbinterKR_91d1f7ee-5cd2-4f87-bc4c-16972039f5e3.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: usbbusif.h
req.include-header: Usbbusif.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: "< = DISPATCH_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	usbbusif.h
apiname:
-	QueryBusInformation
product: Windows
targetos: Windows
req.typenames: "*PUSBD_VERSION_INFORMATION, USBD_VERSION_INFORMATION"
req.product: Windows 10 or later.
---

# PUSB_BUSIFFN_QUERY_BUS_INFORMATION callback


## -description


The <b>QueryBusInformation</b> routine gets information about the bus. 


## -prototype


````
USB_BUSIFFN_QUERY_BUS_INFORMATION QueryBusInformation;

NTSTATUS QueryBusInformation(
  _In_      PVOID  BusContext,
  _In_      ULONG  Level,
  _Inout_   PVOID  BusInformationBuffer,
  _Out_     PULONG BusInformationBufferLength,
  _Out_opt_ PULONG BusInformationActualLength
)
{ ... }
````


## -parameters












#### - BusContext [in]

Handle returned in the <b>BusContext</b> member of the <a href="..\usbbusif\ns-usbbusif-_usb_bus_interface_usbdi_v0.md">USB_BUS_INTERFACE_USBDI_V0</a> structure by an IRP_MN_QUERY_INTERFACE request. 


#### - Level [in]

Specifies the level of information to be returned. If <i>Level</i> is 0, the function returns the total bandwidth and the total consumed bandwidth in bits per second. If <i>Level</i> is 1, the function returns the symbolic name of the controller in Unicode, in addition to the total bandwidth and the total consumed bandwidth. 


#### - BusInformationBuffer [in, out]

Pointer to a buffer that receives the requested bus information. 


#### - BusInformationBufferLength [out]

On input, the length of the buffer specified by <i>BusInformationBuffer</i>. On output, the length of the output data. 


#### - BusInformationActualLength [out, optional]

Specifies the length of the output data. 


## -returns



<b>QueryBusInformation</b> returns one of the following values:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
The call completed successfully.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_BUFFER_TOO_SMALL</b></dt>
</dl>
</td>
<td width="60%">
The buffer was too small. This error code is returned in two cases:

Whenever <i>Level</i> = 0, this error code is returned if the size of the buffer pointed to by <i>BusInformationBuffer</i> is less than the size of the <a href="..\usbbusif\ns-usbbusif-_usb_bus_information_level_0.md">USB_BUS_INFORMATION_LEVEL_0</a> structure.

Whenever Level = 1, this error code is returned if the size of the buffer pointed to by <i>BusInformationBuffer</i> less than the size of the <a href="..\usbbusif\ns-usbbusif-_usb_bus_information_level_1.md">USB_BUS_INFORMATION_LEVEL_1</a> structure. 

</td>
</tr>
</table>
 




## -remarks



The exact information returned by this routine depends on the value of the <i>Level</i> parameter. This routine replaces the <b>USBD_QueryBusInformation</b> library function provided by usbd.sys. 

The function definition that is provided on this reference page is an example routine whose parameters are just placeholder names. The actual prototype of the function is declared in usbbusif.h as follows:

<pre class="syntax" xml:space="preserve"><code>typedef NTSTATUS
  (USB_BUSIFFN *PUSB_BUSIFFN_QUERY_BUS_INFORMATION) (
    IN PVOID,
    IN ULONG,
    IN OUT PVOID,
    IN OUT PULONG,
    OUT PULONG
  );</code></pre>



## -see-also

<a href="..\usbbusif\ns-usbbusif-_usb_bus_information_level_0.md">USB_BUS_INFORMATION_LEVEL_0</a>



<a href="..\usbbusif\ns-usbbusif-_usb_bus_information_level_1.md">USB_BUS_INFORMATION_LEVEL_1</a>



<a href="..\usbbusif\ns-usbbusif-_usb_bus_interface_usbdi_v0.md">USB_BUS_INTERFACE_USBDI_V0</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20USB_BUSIFFN_QUERY_BUS_INFORMATION callback function%20 RELEASE:%20(2/8/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

