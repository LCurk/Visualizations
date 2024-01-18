Download Gateway: https://powerbi.microsoft.com/en-us/gateway/
- Personal mode
- Standard mode

Instructions: https://www.cdata.com/kb/tech/googledrive-connect-powerbi-service-gateway.rst

On three dots in PBI: Unckeck "skip test connection" (it is unchecked by default??)

---

# Personal mode

If you have the On-premises data gateway (personal mode) running on your computer and you close your computer, the gateway service will be stopped, and it won't be able to facilitate data refresh or connections between Power BI and on-premises data sources. The personal mode of the On-premises data gateway is designed to run on a user's machine and is tied to the user's session.

In personal mode, the gateway is typically used for development, testing, or small-scale scenarios where a dedicated gateway is not required. It is not suitable for production use or scenarios where the machine running the gateway might be turned off or restarted frequently.

# Standard mode

If you need a more robust and persistent solution for on-premises data connectivity, you might want to consider using the On-premises data gateway in standard mode, which is designed to run as a Windows service and doesn't rely on a user session. This allows it to run independently of whether a user is logged in or not, providing better reliability for data refresh operations.