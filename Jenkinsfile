def POD_LABEL = "node-build-agent"

podTemplate(
    label: POD_LABEL,
     containers: [
         containerTemplate(name: "node", image: "node:15.4.0-alpine3.12", command: "cat", ttyEnabled: true),
      ],
)
{
  node(POD_LABEL) {
    container("node") {
      stage("checkout") {
        checkout scm
        sh 'ls -la'
      }
      stage("build") {
        sh 'npm install'
      }
      stage("test") {
        sh 'npm test'
      }
    }
  }
}
