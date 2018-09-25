---
UID: NF:wdfwmi.WDF_WMI_BUFFER_APPEND_STRING
title: WDF_WMI_BUFFER_APPEND_STRING function
author: windows-driver-content
description: The WDF_WMI_BUFFER_APPEND_STRING function copies a specified Unicode string into a specified buffer in the format that WMI requires.
old-location: wdf\wdf_wmi_buffer_append_string.htm
tech.root: wdf
ms.assetid: 23d65788-23ce-4ed7-8b68-890c1c3a4100
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DFWMIRef_db6f29cb-fcdc-4948-9ea3-9b36e9f969e8.xml, WDF_WMI_BUFFER_APPEND_STRING, WDF_WMI_BUFFER_APPEND_STRING function, kmdf.wdf_wmi_buffer_append_string, wdf.wdf_wmi_buffer_append_string, wdfwmi/WDF_WMI_BUFFER_APPEND_STRING
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
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: None
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	None
-	None.dll
api_name:
-	WDF_WMI_BUFFER_APPEND_STRING
product:
- Windows
targetos: Windows
req.typenames: 
---

# WDF_WMI_BUFFER_APPEND_STRING function


## -description


<p class="CCE_Message">[Applies to KMDF only]</p>

The <b>WDF_WMI_BUFFER_APPEND_STRING</b> function copies a specified Unicode string into a specified buffer in the format that WMI requires.


## -parameters




### -param Buffer [out]

A pointer to a destination buffer that receives the string.


### -param BufferLength [in]

The length, in bytes, of the destination buffer that receives the string.


### -param String [in]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff564879">UNICODE_STRING</a> structure that contains the string to be copied.


### -param RequiredSize [out]

A pointer to a location that receives the number of bytes that are required to store the specified string in the destination buffer.


## -returns



<b>WDF_WMI_BUFFER_APPEND_STRING</b> returns STATUS_SUCCESS if the operation succeeds. If the destination buffer is too small to hold the Unicode string that the <i>String</i> parameter specifies, the function returns STATUS_BUFFER_TOO_SMALL.




## -remarks



WMI requires that strings that an <a href="https://msdn.microsoft.com/13eed838-2943-4bb4-915f-6a84f0f95851">EvtWmiInstanceQueryInstance</a> callback function returns be preceded by a byte count. The <b>WDF_WMI_BUFFER_APPEND_STRING</b> function calculates the byte count, stores it in the destination buffer, and then copies the string from the <a href="https://msdn.microsoft.com/library/windows/hardware/ff564879">UNICODE_STRING</a> structure into the destination buffer. 

When <b>WDF_WMI_BUFFER_APPEND_STRING</b> returns, the location that the <i>RequiredSize</i> parameter points to contains the total number of bytes that were written to the buffer. To find the first buffer address that follows the string, your driver can pass the <i>RequiredSize</i> value to the WDF_PTR_ADD_OFFSET macro that is defined in <i>Wdfcore.h</i>.


#### Examples

The following code example is from the <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/sample-kmdf-drivers">Serial</a> sample driver. This example is an <a href="https://msdn.microsoft.com/13eed838-2943-4bb4-915f-6a84f0f95851">EvtWmiInstanceQueryInstance</a> callback function that obtains a device's symbolic name and copies the name into the callback function's output buffer.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>NTSTATUS
EvtWmiQueryPortName(
    IN  WDFWMIINSTANCE WmiInstance,
    IN  ULONG OutBufferSize,
    IN  PVOID OutBuffer,
    OUT PULONG BufferUsed
    )
{
    WDFDEVICE device;
    PSERIAL_DEVICE_EXTENSION pDevExt;
    WCHAR pRegName[SYMBOLIC_NAME_LENGTH];
    UNICODE_STRING string;
    USHORT nameSize = sizeof(pRegName);
    NTSTATUS status;

    PAGED_CODE();

    device = WdfWmiInstanceGetDevice(WmiInstance);
    pDevExt = SerialGetDeviceExtension(device);

    status = SerialReadSymName(
                               device,
                               pRegName,
                               &amp;nameSize
                               );
    if (!NT_SUCCESS(status)) {
        return status;
    }
    RtlInitUnicodeString(
                         &amp;string,
                         pRegName
                         );
    return WDF_WMI_BUFFER_APPEND_STRING(
                                        OutBuffer,
                                        OutBufferSize,
                                        &amp;string,
                                        BufferUsed
                                        );
}</pre>
</td>
</tr>
</table></span></div>



## -see-also




<a href="https://msdn.microsoft.com/13eed838-2943-4bb4-915f-6a84f0f95851">EvtWmiInstanceQueryInstance</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff564879">UNICODE_STRING</a>
 

 

