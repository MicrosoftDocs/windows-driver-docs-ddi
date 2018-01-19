---
UID: NS:61883._CMP_GET_PLUG_HANDLE
title: _CMP_GET_PLUG_HANDLE
author: windows-driver-content
description: This structure is used in getting the handle of a plug.
old-location: ieee\cmp_get_plug_handle.htm
old-project: IEEE
ms.assetid: 4EDEE2EE-7B42-4CC9-8CFC-4690193C5D4D
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: _CMP_GET_PLUG_HANDLE, *PCMP_GET_PLUG_HANDLE, CMP_GET_PLUG_HANDLE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: 61883.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: CMP_GET_PLUG_HANDLE
req.alt-loc: 61883.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
req.typenames: *PCMP_GET_PLUG_HANDLE, CMP_GET_PLUG_HANDLE
---

# _CMP_GET_PLUG_HANDLE structure



## -description
This structure is used in getting the handle of a plug. The  request retrieves a unique handle associated with an input or output plug. The plug handle is required for all operations on the plug. A driver uses a plug handle to get the state of a plug, modify plug settings, or delete a plug. A driver can delete only plugs it has previously created. 



## -syntax

````
typedef struct _CMP_GET_PLUG_HANDLE {
  ULONG         PlugNum;
  CMP_PLUG_TYPE Type;
  HANDLE        hPlug;
} CMP_GET_PLUG_HANDLE, *PCMP_GET_PLUG_HANDLE;
````


## -struct-fields

### -field PlugNum

The number of the plug whose handle was returned by the Av61883_CreatePlug request that created the plug.


### -field Type

The type of the plug. This can be CMP_PlugOut for an output plug, or CMP_PlugIn for an input plug.


### -field hPlug

On output, a handle to the plug specified with PlugNum and Type.


## -remarks
If successful, the IEC-61883 protocol driver sets <b>Irp-&gt;IoStatus.Status </b>to STATUS_SUCCESS. 

If an incorrect parameter is passed in, the protocol driver sets <b>Irp-&gt;IoStatus.Status </b>to STATUS_INVALID_PARAMETER.


## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff537008">AV_61883_REQUEST</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [IEEE\buses]:%20CMP_GET_PLUG_HANDLE structure%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

