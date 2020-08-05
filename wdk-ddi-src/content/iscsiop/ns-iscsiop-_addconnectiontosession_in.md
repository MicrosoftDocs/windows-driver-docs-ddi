---
UID: NS:iscsiop._AddConnectionToSession_IN
title: _AddConnectionToSession_IN (iscsiop.h)
description: The AddConnectionToSession_IN structure holds input data for the AddConnectionToSession method, which is used to add a new connection to an already existing session.
old-location: storage\addconnectiontosession_in.htm
tech.root: storage
ms.assetid: 7fcb0b87-1f9e-4956-a59a-cd83fa04e5db
ms.date: 03/29/2018
keywords: ["AddConnectionToSession_IN structure"]
ms.keywords: "*PAddConnectionToSession_IN, AddConnectionToSession_IN, AddConnectionToSession_IN structure [Storage Devices], PAddConnectionToSession_IN, PAddConnectionToSession_IN structure pointer [Storage Devices], _AddConnectionToSession_IN, iscsiop/AddConnectionToSession_IN, iscsiop/PAddConnectionToSession_IN, storage.addconnectiontosession_in, structs-iSCSI_4e238073-ca54-4da3-afcc-4b45e4da243f.xml"
f1_keywords:
 - "iscsiop/AddConnectionToSession_IN"
 - "AddConnectionToSession_IN"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- iscsiop.h
api_name:
- AddConnectionToSession_IN
targetos: Windows
req.typenames: AddConnectionToSession_IN, *PAddConnectionToSession_IN
---

# _AddConnectionToSession_IN structure


## -description


The AddConnectionToSession_IN structure holds input data for the <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/addconnectiontosession">AddConnectionToSession</a> method, which is used to add a new connection to an already existing session.


## -struct-fields




### -field UniqueAdapterId

A 64-bit integer that uniquely identifies an adapter and a particular loaded instance of a storage miniport driver that manages the adapter. This identifier is unique, not only on the computer where the adapter is located, but also across the entire network. 


### -field UniqueSessionId

A 64-bit integer that uniquely identifies the session. The <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/logintotarget">LoginToTarget</a> and <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/addconnectiontosession">AddConnectionToSession</a> methods both return this value in their <i>UniqueSessionId</i> parameter. Do not confuse this value with the values in the ISID and TSID members.


### -field SecurityFlags

A bitwise OR of flags that indicate the security requirements of a target. For a list of possible values for this member, see <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/security-flag-qualifiers">SECURITY_FLAG_QUALIFIERS</a>.


### -field PortNumber

The number of the port from which to initiate the target logon session. 


### -field LoginOptions

A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/iscsidef/ns-iscsidef-_iscsi_loginoptions">ISCSI_LoginOptions</a> structure that describes the characteristics of the target logon session that a connection will be added to. 


### -field TargetPortal

A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/iscsidef/ns-iscsidef-_iscsi_targetportal">ISCSI_TargetPortal</a> structure that indicates which target portal to use to make the additional connection. The <b>AddConnectionToSession</b> method calls the <b>LoginToTarget</b> method to establish the new connection. If <b>LoginToTarget</b> fails with a status value of either ISCSC_TARGET_MOVED_PERMANENTLY or ISCSC_TARGET_MOVED_TEMPORARILY. <b>TargetPortal</b> will indicate, on output from <b>AddConnectionToSession</b>, the portal that the logon operation should be redirected to. For more information about the ISCSC_TARGET_MOVED_PERMANENTLY and ISCSC_TARGET_MOVED_TEMPORARILY status values, see <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/iscsi-status-qualifiers">ISCSI_STATUS_QUALIFIERS</a>.


### -field UsernameSize

The username size, in bytes.


### -field PasswordSize

The password size, in bytes.


### -field KeySize

The preshared key size, in bytes.


### -field Key

A variable-length array of characters that specifies the preshared key that is associated with the target IP address. The number of elements in the array is specified by the KeySize field.


## -remarks



The iSCSI service requires this method. It is optional that you implement this method.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/storage/addconnectiontosession">AddConnectionToSession</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/iscsiop/ns-iscsiop-_addconnectiontosession_out">AddConnectionToSession_OUT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/iscsidef/ns-iscsidef-_iscsi_loginoptions">ISCSI_LoginOptions</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/iscsidef/ns-iscsidef-_iscsi_targetportal">ISCSI_TargetPortal</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/storage/logintotarget">LoginToTarget</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/storage/msiscsi-operations-wmi-class">MSiSCSI_Operations WMI Class</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/storage/security-flag-qualifiers">SECURITY_FLAG_QUALIFIERS</a>
 

 

