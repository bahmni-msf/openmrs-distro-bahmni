FROM bahmni/openmrs:1.0.0

# Remove omods
RUN rm -f ${OPENMRS_APPLICATION_DATA_DIRECTORY}/modules/appointments-*.omod
RUN rm -f ${OPENMRS_APPLICATION_DATA_DIRECTORY}/modules/bahmni.ie.apps-*.omod
RUN rm -f ${OPENMRS_APPLICATION_DATA_DIRECTORY}/modules/bahmnicore-*.omod
RUN rm -f ${OPENMRS_APPLICATION_DATA_DIRECTORY}/modules/visit-close-module-*.omod
RUN rm -f ${OPENMRS_APPLICATION_DATA_DIRECTORY}/modules/bahmnimsf-*.omod

# Copy omods
COPY target/appointments-*.omod  ${OPENMRS_APPLICATION_DATA_DIRECTORY}/modules
COPY target/bahmni.ie.apps-*.omod  ${OPENMRS_APPLICATION_DATA_DIRECTORY}/modules
COPY target/bahmnicore-*.omod  ${OPENMRS_APPLICATION_DATA_DIRECTORY}/modules
COPY target/visit-close-module-*.omod ${OPENMRS_APPLICATION_DATA_DIRECTORY}/modules
COPY target/bahmnimsf-*.omod ${OPENMRS_APPLICATION_DATA_DIRECTORY}/modules

RUN mkdir -p /home/bahmni/document_images
RUN mkdir -p /home/bahmni/uploaded_results
RUN mkdir -p /home/bahmni/uploaded-files

COPY package/docker/openmrs/bahmni_startup.sh /openmrs/
RUN chmod +x /openmrs/bahmni_startup.sh
