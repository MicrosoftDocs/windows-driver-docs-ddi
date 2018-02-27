---
UID: NF:wdfrequest.WdfRequestGetFileObject
title: WdfRequestGetFileObject function
author: windows-driver-content
description: The WdfRequestGetFileObject method retrieves the framework file object that is associated with a specified I/O request.
old-location: wdf\wdfrequestgetfileobject.htm
old-project: wdf
ms.assetid: 0c5a1e12-b66f-4bcb-bb9d-739b883fe9c2
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: DFRequestObjectRef_cfa39375-4338-428c-aec5-52479b2a91ea.xml, WdfRequestGetFileObject, WdfRequestGetFileObject method, kmdf.wdfrequestgetfileobject, wdf.wdfrequestgetfileobject, wdfrequest/WdfRequestGetFileObject
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfrequest.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.ddi-compliance: DriverCreate, FileObjectConfigured, InvalidReqAccess, InvalidReqAccessLocal, KmdfIrql, KmdfIrql2
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
-	WdfRequestGetFileObject
product: Windows
targetos: Windows
req.typenames: WDF_REQUEST_TYPE
req.product: Windows 10 or later.
---

# WdfRequestGetFileObject function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WdfRequestGetFileObject</b> method retrieves the framework file object that is associated with a specified I/O request.


## -syntax


````
WDFFILEOBJECT WdfRequestGetFileObject(
  _In_ WDFREQUEST Request
);
````


## -parameters




### -param Request [in]

A handle to a framework request object.


## -returns



<b>WdfRequestGetFileObject</b> returns a handle to the framework file object, if the framework has created a file object for the specified request. Otherwise, this method returns <b>NULL</b>. (A driver typically tests for a <b>NULL</b> return value only if it sets the <a href="..\wdfdevice\ne-wdfdevice-_wdf_fileobject_class.md">WdfFileObjectCanBeOptional</a> bit flag in the <a href="..\wdfdevice\ns-wdfdevice-_wdf_fileobject_config.md">WDF_FILEOBJECT_CONFIG</a> structure.)

A bug check occurs if the driver supplies an invalid object handle.






## -remarks



The <b>WdfRequestGetFileObject</b> method returns <b>NULL</b> if either:

<ul>
<li>
Your driver has not called <a href="..\wdfdevice\nf-wdfdevice-wdfdeviceinitsetfileobjectconfig.md">WdfDeviceInitSetFileObjectConfig</a> and specified a <a href="..\wdfdevice\ne-wdfdevice-_wdf_fileobject_class.md">WDF_FILEOBJECT_CLASS</a> value that causes the framework to create file objects.

</li>
<li>
Another driver sent a read, write, or I/O control request to your driver without first sending a request type of <a href="..\wdfrequest\ne-wdfrequest-_wdf_request_type.md">WdfRequestTypeCreate</a>.

</li>
</ul>
For more information about <b>WdfRequestGetFileObject</b> and framework file objects, see <a href="https://msdn.microsoft.com/93ec5dd7-8ef0-4cea-9253-ea5d7869d4b8">Framework File Objects</a>.


#### Examples

The following code example obtains an I/O request's file object and then calls a driver-defined routine that obtains a pointer to the file object's context space.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>VOID
MyEvtIoWrite(
    IN WDFQUEUE  Queue,
    IN WDFREQUEST  Request,
    IN size_t  Length
    )
{
    WDFFILEOBJECT  fileObject;
    PFILE_OPEN_CONTEXT  pOpenContext;

    fileObject = WdfRequestGetFileObject(Request);
    pOpenContext = GetFileObjectContext(fileObject)-&gt;OpenContext;
}</pre>
</td>
</tr>
</table></span></div>



## -see-also

<a href="..\wdfdevice\nf-wdfdevice-wdfdeviceinitsetfileobjectconfig.md">WdfDeviceInitSetFileObjectConfig</a>



<a href="..\wdfdevice\ne-wdfdevice-_wdf_fileobject_class.md">WDF_FILEOBJECT_CLASS</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfRequestGetFileObject method%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

