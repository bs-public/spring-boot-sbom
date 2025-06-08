# Spring Boot SBOM

SBOM stands for `Software Bill of Materials` and describes the components used to build a software artifact.
These SBOMs are useful because they describe exactly what your application contains. With that information, you can assess if a security vulnerability affects your application, or use automated security tools to scan your applications and alert you on security vulnerabilities.

There are multiple SBOM formats out there, the most widely used ones are CycloneDX, SPDX, and Syft. The support consists of three pillars:

- The configuration of the CycloneDX plugin to generate the SBOM when the application is built
- The packaging of the generated SBOM file into the uber jar
- An actuator endpoint to expose the generated SBOM (if enabled)


## SBOM API Endpoints

### Retrieve Available SBOMs
**GET** `/actuator/sbom`
Returns a list of available SBOM document IDs.

**Response:**
```json
{
    "ids": [
        "application"
    ]
}
```

### Retrieving a Single SBOM
**GET** `/actuator/sbom/{id}`

Returns the detailed Software Bill of Materials (SBOM) for the application in CycloneDX format (or other supported SBOM formats).

**Response:**

See [`sbom.json`](./sbom.json)
