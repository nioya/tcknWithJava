# Turkish Identification Number Validation Java Class

Turkish Identification Number (Turkish: Türkiye Cumhuriyeti Kimlik Numarası or abbreviated as T.C. Kimlik No. or TCKN) is a unique personal identification number that is assigned to every citizen of Turkey. For details, you can visit Wikipedia (https://en.wikipedia.org/wiki/Turkish_Identification_Number)

This code helps to validate a TCKN with required data by accessing web service which states by Central Registration Administration System of Republic of Turkey

## Details
Code firstly check identity number has valid structure or not, then if it is ok, calls offical web service to verify number is correct or not.
Web Service Classes are generated by using wsimport tool of JDK.
Below command can be run on command line
```
wsimport.exe keep -Xnocompile KPSPublic.wsdl
```
## Offical Web Service
You can access offical web site and check WSDL as well. https://tckimlik.nvi.gov.tr/Service/KPSPublic.asmx
## Usage
```

  TCKNController tcknController = null;
		try {
			tcknController = new TCKNController();
		} catch (MalformedURLException e) {
			// TODO Auto-generated catch block
			e.printStackTrace();
		}
		if(tcknController != null){
			boolean result = tcknController.checkTCKNVality("TCKN","NAME","SURNAME", "BIRTHYEAR");
			if(result){
				System.out.println("Result: VALID");
			}else{
				System.out.println("Result: INVALID");
			}			
		}

```
