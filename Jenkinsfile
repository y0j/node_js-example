def label = "POD_LABEL"

podTemplate(
    label: label,
     containers: [
         containerTemplate(name: "node", image: "node:15.4.0-alpine3.12", command: "cat", ttyEnabled: true),
      ],
)
{
  node(label) {
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
