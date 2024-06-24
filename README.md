# ds-ml-beer-challenge
Este repositorio contiene dos casos de análisis:
- Caso de Análisis: Solicitud de tarjeta de crédito
- Caso de Análisis: Tasa de Crimen

Previamente se debe configurar el entorno de desarrollo.

Instalación pycaret sobre python 3.9

Error al instalar lightgbm.

Paso 0: Si no tienes instalado brew:

1. Abre tu terminal (no sobre tu environment)  y ejecuta el siguiente comando para instalar Homebrew:
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"

2. Agregar Homebrew al PATH:
nano ~/.zshrc
export PATH="/usr/local/bin:/opt/homebrew/bin:$PATH"

3. Recarga tu configuración en shell
source ~/.bash_profile  # o source ~/.zshrc, dependiendo de tu shell

Paso 1:

1. Ingresa a tu entorno virtual
conda activate myenv

2. Instalar las siguientes librerías empleando 'brew' y 'pip'
brew install libomp

3. Después de instalar libomp, debes exportar las variables de entorno para que LightGBM pueda encontrar las librerías necesarias:
nano ~/.zshrc
export CMAKE_ARGS="-DOpenMP_C_FLAGS=-Xpreprocessor\ -fopenmp\ -I$(brew --prefix libomp)/include -DOpenMP_C_LIB_NAMES=omp -DOpenMP_CXX_FLAGS=-Xpreprocessor\ -fopenmp\ -I$(brew --prefix libomp)/include -DOpenMP_CXX_LIB_NAMES=omp -DOpenMP_omp_LIBRARY=$(brew --prefix libomp)/lib/libomp.dylib"

4. Instalar la librería
pip install lightgbm
