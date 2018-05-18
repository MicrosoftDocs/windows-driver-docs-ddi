> [!NOTE]
> This function is called through the VMBus Kernel Mode Client Library (KMCL) interface, provided by the Vmbkmcl.sys bus driver. 
>
> To access the KMCL, allocate a **KMCL_CLIENT_INTERFACE_V1** structure to receive the interface, then call either [**WdfFdoQueryForInterface**](../wdffdo/nf-wdffdo-wdffdoqueryforinterface.md) or [**WdfIoTargetQueryForInterface**](../wdfiotarget/nf-wdfiotarget-wdfiotargetqueryforinterface.md) with the *InterfaceType* parameter set to **KMCL_CLIENT_INTERFACE_TYPE**, the *Size* parameter set to `sizeof(KMCL_CLIENT_INTERFACE_V1)`, and the *Version* parameter set to **KMCL_CLIENT_INTERFACE_VERSION_LATEST**. 
>
> For more information about driver-defined interfaces, see [Using Driver-Defined Interfaces](https://docs.microsoft.com/windows-hardware/drivers/wdf/using-driver-defined-interfaces).