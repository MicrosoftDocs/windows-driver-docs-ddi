---
UID: NF:wdffileobject.WdfFileObjectGetFileName
title: WdfFileObjectGetFileName function
author: windows-driver-content
description: The WdfFileObjectGetFileName method returns the file name that a specified framework file object contains.
old-location: wdf\wdffileobjectgetfilename.htm
old-project: wdf
ms.assetid: 9d4e45c7-ed1f-476a-8522-4213ac42a3c3
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: PFN_WDFFILEOBJECTGETFILENAME, kmdf.wdffileobjectgetfilename, WdfFileObjectGetFileName method, DFFileObjectRef_07be4c38-fa04-41d3-8f8e-f7ec5ed6ff18.xml, wdffileobject/WdfFileObjectGetFileName, WdfFileObjectGetFileName, wdf.wdffileobjectgetfilename
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdffileobject.h
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
-	WdfFileObjectGetFileName
product: Windows
targetos: Windows
req.typenames: WDF_FILE_INFORMATION_CLASS, *PWDF_FILE_INFORMATION_CLASS
req.product: Windows 10 or later.
---

# WdfFileObjectGetFileName function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WdfFileObjectGetFileName</b> method returns the file name that a specified framework file object contains.


## -syntax


````
PUNICODE_STRING WdfFileObjectGetFileName(
  _In_ WDFFILEOBJECT FileObject
);
````


## -parameters




### -param FileObject [in]

A handle to a framework file object.


## -returns


<b>WdfFileObjectGetFileName</b> returns a pointer to a <a href="..\wudfwdm\ns-wudfwdm-_unicode_string.md">UNICODE_STRING</a> structure that contains the file name. The method returns <b>NULL</b> if there is no WDM file object for the specified framework file object, or if it is called at an IRQL higher than PASSIVE_LEVEL.

A bug check occurs if the driver supplies an invalid object handle.





## -remarks


If a driver specified a reference string when it called <a href="..\wdfdevice\nf-wdfdevice-wdfdevicecreatedeviceinterface.md">WdfDeviceCreateDeviceInterface</a>, <b>WdfFileObjectGetFileName</b> returns the reference string prepended by a backslash. To determine the reference string, remove the backslash.

The returned string can contain a file name or a reference string. The string does not contain the device name. If an application or kernel-mode component has opened the device instead of a file, with no reference string, the <b>Length</b> member of the returned UNICODE_STRING structure is zero.

Your driver should only call <b>WdfFileObjectGetFileName</b> while it is processing a file creation request (<b>WdfRequestTypeCreate</b> request type). Your driver might process <b>WdfRequestTypeCreate</b>-typed I/O requests in an <a href="..\wdfdevice\nc-wdfdevice-evt_wdf_device_file_create.md">EvtDeviceFileCreate</a> callback function.

Or, instead of providing an <a href="..\wdfdevice\nc-wdfdevice-evt_wdf_device_file_create.md">EvtDeviceFileCreate</a> callback function, the driver can call <a href="..\wdfdevice\nf-wdfdevice-wdfdeviceconfigurerequestdispatching.md">WdfDeviceConfigureRequestDispatching</a> to set an I/O queue to receive all file creation requests (<b>WdfRequestTypeCreate</b> request type). The driver will subsequently receive file creation requests in the queue's <a href="..\wdfio\nc-wdfio-evt_wdf_io_queue_io_default.md">EvtIoDefault</a> request handler.

 For more information about framework file objects, see <a href="https://msdn.microsoft.com/93ec5dd7-8ef0-4cea-9253-ea5d7869d4b8">Framework File Objects</a>.

For more information about file names, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff542068">Controlling Device Namespace Access</a>.

For more information about reference strings, see <a href="..\wdm\nf-wdm-ioregisterdeviceinterface.md">IoRegisterDeviceInterface</a>.



## -see-also

<a href="..\wdfdevice\nf-wdfdevice-wdfdevicecreatedeviceinterface.md">WdfDeviceCreateDeviceInterface</a>

<a href="..\wudfwdm\ns-wudfwdm-_unicode_string.md">UNICODE_STRING</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfFileObjectGetFileName method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

