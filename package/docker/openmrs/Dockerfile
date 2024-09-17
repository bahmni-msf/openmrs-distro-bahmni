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

RUN setfacl -R -d -m o::rx -m g::rx /home/bahmni/document_images
RUN setfacl -R -d -m o::rx -m g::rx /home/bahmni/uploaded_results
RUN setfacl -R -d -m o::rx -m g::rx /home/bahmni/uploaded-files
