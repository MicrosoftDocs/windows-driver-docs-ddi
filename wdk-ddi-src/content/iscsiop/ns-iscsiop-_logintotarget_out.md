---
UID: NS:iscsiop._LoginToTarget_OUT
title: "_LoginToTarget_OUT"
author: windows-driver-content
description: The LoginToTarget_OUT structure holds the output data for the LoginToTarget method.
old-location: storage\logintotarget_out.htm
old-project: storage
ms.assetid: 569816dc-3b92-45da-a1b8-ce4b504b6592
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: PLoginToTarget_OUT structure pointer [Storage Devices], storage.logintotarget_out, PLoginToTarget_OUT, iscsiop/PLoginToTarget_OUT, *PLoginToTarget_OUT, LoginToTarget_OUT, LoginToTarget_OUT structure [Storage Devices], iscsiop/LoginToTarget_OUT, _LoginToTarget_OUT, structs-iSCSI_8fefca89-dd27-4a01-90a1-76ed16e79568.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: iscsiop.h
req.include-header: Iscsiop.h
req.target-type: Windows
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
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	iscsiop.h
apiname:
-	LoginToTarget_OUT
product: Windows
targetos: Windows
req.typenames: "*PLoginToTarget_OUT, LoginToTarget_OUT"
---

# _LoginToTarget_OUT structure


## -description


The LoginToTarget_OUT structure holds the output data for the <a href="https://msdn.microsoft.com/library/windows/hardware/ff561599">LoginToTarget</a> method.


## -syntax


````
typedef struct _LoginToTarget_OUT {
  ULONG     Status;
  ULONGLONG UniqueSessionId;
  ULONGLONG UniqueConnectionId;
} LoginToTarget_OUT, *PLoginToTarget_OUT;
````


## -struct-fields




### -field Status

On output from <b>LoginToTarget</b>, the status of the <b>LoginToTarget</b> operation. For a list of status qualifiers, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff561568">ISCSI_STATUS_QUALIFIERS</a>.


### -field UniqueSessionId

A 64-bit integer that uniquely identifies the session. The <a href="https://msdn.microsoft.com/library/windows/hardware/ff561599">LoginToTarget</a> and <a href="https://msdn.microsoft.com/library/windows/hardware/ff550121">AddConnectionToSession</a> methods both return this value in their <i>UniqueSessionId</i> parameter. The unique session identifier (ID) does not change until the initiator logs off of the session. The session ID that the iSCSI initiator service exposes to user-mode software is a 128-bit number. The top (most significant) 64 bits consist of a unique adapter ID that the initiator reports in the <b>UniqueAdapterId</b> member of the <a href="..\iscsimgt\ns-iscsimgt-_msiscsi_hbainformation.md">MSiSCSI_HBAInformation</a> class. The lower (least significant) 64 bits correspond to the value in <b>UniqueSessionId</b>. When the service communicates with the adapter, the service uses the lower 64 bits (<b>UniqueSessionId</b>), while user-mode software uses all of the 128 bits to communicate with the iSCSI initiator service.


### -field UniqueConnectionId

On output from <b>LoginToTarget</b>, a 64-bit integer that uniquely identifies the connection. The connection ID that the iSCSI initiator service exposes to user-mode software is a 128-bit number. The top (most significant) 64 bits consist of a unique adapter ID that the initiator reports in the <b>UniqueAdapterId</b> member of the <a href="..\iscsimgt\ns-iscsimgt-_msiscsi_hbainformation.md">MSiSCSI_HBAInformation</a> class. The lower (least significant) 64 bits correspond to the value in <b>UniqueConnectionId</b>. When the service communicates with the adapter, the service uses the lower 64 bits (<b>UniqueConnectionId</b>), while user-mode software uses all the 128 bits to communicate with the iSCSI initiator service.


## -remarks



You must implement this method.




## -see-also

<a href="..\iscsiop\ns-iscsiop-_logintotarget_in.md">LoginToTarget_IN</a>



<a href="..\iscsimgt\ns-iscsimgt-_msiscsi_hbainformation.md">MSiSCSI_HBAInformation</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563091">MSiSCSI_Operations WMI Class</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561599">LoginToTarget</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561568">ISCSI_STATUS_QUALIFIERS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550121">AddConnectionToSession</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20LoginToTarget_OUT structure%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

