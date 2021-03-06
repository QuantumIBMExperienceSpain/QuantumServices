#Quantum IBM Service

This project allow test experiment with the [API IBM Quantum Experience Procesor.](URL "https://github.com/gbarcomu/QInterpreter")

The project is a colaboration with the [QInterpreter](URL "https://github.com/gbarcomu/QInterpreter")
. The module, use de interpreter for convert files .q in json and simulate this .json in the IBM Quantum Experience.

This module have a simple use.

#server.js

```[JS] 
var quantumService = require('quantumIBMService');

quantumService.newQuantumExperiment("nameExperiment", 
									"usermail", "password","srcJson");
```
**nameExperiment:** Name the experiment taht you want test.

**usermail:** The user mail sign up in the platform.

**password** The password user.

**srcJson:** is the source file json is the source generated by the Interpreter from .q file mor info in the QInterpreter repo.

This method return a JSON file with the folowing format and the name ExperimentNameResult.Json

#ExampleResult.json

```[json]
{"execution": {
        "result": {
            "date": "2016-05-03T07:57:38.373Z",
            "data": {
                "p": {
                    "qubits": [1,2],
                    "labels": ["00","01","10","11"],
                    "values": [0.46578058604498057, 0.010055914979718002,
                        0.036575746838289756, 0.48758775213701194 ]
                },
                "t": 390,
                "qasm": "qreg q,5; gate h,0.7071067811865476,0.7071067811865476],[0.7071067811865476,-0.7071067811865476]];gate measure, [[1,0],[0,0.7071067811865476+0.7071067811865476i]];gate cx, [[1,0,0,0],[0,1,0,0],[0,0,0,1],[0,0,1,0]]; h q[1];cx q[1], q[2];measure q[1];measure q[2];",
                "serialNumberDevice": "chip_simulator_docker_716435e",
                "time": 3.918743848800659
            }
        },
        "startDate": "2016-06-23T22:22:26.350Z",
        "modificationDate": 1466720546350,
        "endDate": "2016-06-23T22:22:27.907Z",
        "status": {
            "id": "DONE"
        },
        "deviceRunType": "sim_realistic",
...
}            
```

Thanks to [gbarcomu](URL "https://github.com/gbarcomu") for his Quantum interpreter [Qinterpreter](URL "https://github.com/gbarcomu/QInterpreter") and all QUantum Experience API info.