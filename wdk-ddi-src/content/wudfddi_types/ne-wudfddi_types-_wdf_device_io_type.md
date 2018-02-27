---
UID: NE:wudfddi_types._WDF_DEVICE_IO_TYPE
title: "_WDF_DEVICE_IO_TYPE"
author: windows-driver-content
description: The WDF_DEVICE_IO_TYPE enumeration is used to specify a method for accessing data buffers.
old-location: wdf\wdf_device_io_type__umdf_.htm
old-project: wdf
ms.assetid: 52733647-d577-4507-a5ad-5f56f3a9f8a2
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: "*PWDF_DEVICE_IO_TYPE, PWDF_DEVICE_IO_TYPE, PWDF_DEVICE_IO_TYPE enumeration pointer, WDF_DEVICE_IO_TYPE, WDF_DEVICE_IO_TYPE enumeration, WdfDeviceIoBuffered, WdfDeviceIoBufferedOrDirect, WdfDeviceIoDirect, WdfDeviceIoMaximum, WdfDeviceIoNeither, WdfDeviceIoUndefined, _WDF_DEVICE_IO_TYPE, umdf.wdf_device_io_type__umdf_, umdfstructs_df3f719d-59c4-4df5-b079-33e6962d1225.xml, wdf.wdf_device_io_type__umdf_, wudfddi_types/PWDF_DEVICE_IO_TYPE, wudfddi_types/WDF_DEVICE_IO_TYPE, wudfddi_types/WdfDeviceIoBuffered, wudfddi_types/WdfDeviceIoBufferedOrDirect, wudfddi_types/WdfDeviceIoDirect, wudfddi_types/WdfDeviceIoMaximum, wudfddi_types/WdfDeviceIoNeither, wudfddi_types/WdfDeviceIoUndefined"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: wudfddi_types.h
req.include-header: Wudfddi.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 1.9
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: Unavailable in UMDF 2.0 and later.
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.exe
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	Wudfddi_types.h
apiname:
-	WDF_DEVICE_IO_TYPE
product: Windows
targetos: Windows
req.typenames: WDF_DEVICE_IO_TYPE, *PWDF_DEVICE_IO_TYPE
req.product: Windows 10 or later.
---

# _WDF_DEVICE_IO_TYPE enumeration


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]


The <b>WDF_DEVICE_IO_TYPE</b> enumeration is used to specify a method for <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/accessing-data-buffers-in-wdf-drivers">accessing data buffers</a>.


## -syntax


````
typedef enum _WDF_DEVICE_IO_TYPE { 
  WdfDeviceIoUndefined         = 0x00,
  WdfDeviceIoNeither           = 0x01,
  WdfDeviceIoBuffered          = 0x02,
  WdfDeviceIoDirect            = 0x03,
  WdfDeviceIoBufferedOrDirect  = 0x04,
  WdfDeviceIoMaximum           = 0x5
} WDF_DEVICE_IO_TYPE, *PWDF_DEVICE_IO_TYPE;
````


## -enum-fields




### -field WdfDeviceIoUndefined

Reserved for system use.


### -field WdfDeviceIoNeither

Reserved for system use.


### -field WdfDeviceIoBuffered

UMDF and the driver use <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/accessing-data-buffers-in-wdf-drivers">buffered I/O</a> to access data buffers.


### -field WdfDeviceIoDirect

UMDF and the driver use <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/accessing-data-buffers-in-wdf-drivers">direct I/O</a> to access data buffers.


### -field WdfDeviceIoBufferedOrDirect

UMDF and the driver can use either buffered I/O or direct I/O to access data buffers. 


### -field WdfDeviceIoMaximum

Reserved for system use.


## -remarks



The <b>WDF_DEVICE_IO_TYPE</b> enumeration is used as input to <a href="https://msdn.microsoft.com/library/windows/hardware/ff556969">IWDFDeviceInitialize2::SetIoTypePreference</a> and as output from <a href="https://msdn.microsoft.com/library/windows/hardware/ff558994">IWDFIoRequest2::GetEffectiveIoType</a>.

You should use the following guidelines when choosing an I/O type for your driver:

<ul>
<li>
Buffered I/O provides the best security and reliability, because applications and drivers access separate copies of the data. In addition, buffered I/O provides the best performance if most of the data transfers are relatively small (typically two memory pages or less). 

</li>
<li>
Direct I/O provides the best performance if most I/O requests transfer large amounts of data. However, applications and drivers access a single copy of the data. Therefore, the driver must copy application-specified parameters to local driver memory before it validates the parameters to ensure that the application does not modify the parameters after validation. If the driver must validate large amounts of application data, buffered I/O might be a better choice because the driver does not have to copy the data before validating it.

</li>
<li>
Typically, a filter driver that can reside in several driver stacks and performs little processing of application data can support both buffered I/O and direct I/O and therefore can specify <b>WdfDeviceIoBufferedOrDirect</b>. However, if the driver validates application-specified parameters it must copy them first when direct I/O is used.

</li>
</ul>
For more information about accessing an I/O request's data buffers, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/accessing-data-buffers-in-wdf-drivers">Accessing Data Buffers in UMDF-Based Drivers</a>.

For the KMDF version of this enumeration, see <a href="..\wudfddi_types\ne-wudfddi_types-_wdf_device_io_type.md">WDF_DEVICE_IO_TYPE</a>.




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff556969">IWDFDeviceInitialize2::SetIoTypePreference</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff558994">IWDFIoRequest2::GetEffectiveIoType</a>



<a href="..\wudfddi_types\ne-wudfddi_types-_wdf_device_io_buffer_retrieval.md">WDF_DEVICE_IO_BUFFER_RETRIEVAL</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WDF_DEVICE_IO_TYPE enumeration%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

