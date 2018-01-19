---
UID: NF:d3dkmthk.D3DKMTSharedPrimaryLockNotification
title: D3DKMTSharedPrimaryLockNotification function
author: windows-driver-content
description: The D3DKMTSharedPrimaryLockNotification function notifies the operating system about an upcoming lock to a shared primary surface.
old-location: display\d3dkmtsharedprimarylocknotification.htm
old-project: display
ms.assetid: 4104b137-dd32-4566-a46a-f20ef6b602c6
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: D3DKMTSharedPrimaryLockNotification
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: D3DKMTSharedPrimaryLockNotification
req.alt-loc: Gdi32.dll,API-MS-Win-dx-d3dkmt-l1-1-0.dll,API-MS-Win-dx-d3dkmt-l1-1-1.dll,API-MS-Win-DX-D3DKMT-L1-1-2.dll
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Gdi32.lib
req.dll: Gdi32.dll
req.irql: 
req.typenames: D3DKMT_DRIVERVERSION
---

# D3DKMTSharedPrimaryLockNotification function



## -description
The <b>D3DKMTSharedPrimaryLockNotification</b> function notifies the operating system about an upcoming lock to a shared primary surface.



## -syntax

````
NTSTATUS APIENTRY D3DKMTSharedPrimaryLockNotification(
  _In_ const D3DKMT_SHAREDPRIMARYLOCKNOTIFICATION *pData
);
````


## -parameters

### -param pData [in]

A pointer to a <a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_sharedprimarylocknotification.md">D3DKMT_SHAREDPRIMARYLOCKNOTIFICATION</a> structure that describes the shared primary surface that an application will lock. 


## -returns
<b>D3DKMTSharedPrimaryLockNotification</b> returns one of the following values:
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>Notification about an upcoming lock to a shared primary surface was successfully performed.
<dl>
<dt><b>STATUS_NO_MEMORY</b></dt>
</dl>
<a href="..\d3dkmthk\nf-d3dkmthk-d3dkmtsharedprimarylocknotification.md">D3DKMTSharedPrimaryLockNotification</a> could not complete because of insufficient memory.
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>Parameters were validated and determined to be incorrect.

 

This function might also return other NTSTATUS values that are defined in Ntstatus.h.


## -remarks
The OpenGL ICD calls the <b>D3DKMTSharedPrimaryLockNotification</b> function to inform the operating system that an application is about to lock the GDI shared primary surface that exists on the graphics adapter and video present source that the <b>AdapterLuid</b> and <b>VidPnSourceId</b> members of the <a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_sharedprimarylocknotification.md">D3DKMT_SHAREDPRIMARYLOCKNOTIFICATION</a> structure specify. The OpenGL ICD must call <b>D3DKMTSharedPrimaryLockNotification</b> before it calls the <a href="..\d3dkmthk\nf-d3dkmthk-d3dkmtlock.md">D3DKMTLock</a> function for the GDI shared primary surface to ensure that the operating system disables all sprites that intersect with the lock region that the <b>LockRect</b> member of D3DKMT_SHAREDPRIMARYLOCKNOTIFICATION specifies.


## -see-also
<dl>
<dt>
<a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_sharedprimarylocknotification.md">D3DKMT_SHAREDPRIMARYLOCKNOTIFICATION</a>
</dt>
<dt>
<a href="..\d3dkmthk\nf-d3dkmthk-d3dkmtlock.md">D3DKMTLock</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DKMTSharedPrimaryLockNotification function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

