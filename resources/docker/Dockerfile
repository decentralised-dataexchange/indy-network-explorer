FROM bcgovimages/von-image:node-1.12-6

ENV LOG_LEVEL ${LOG_LEVEL:-info}
ENV RUST_LOG ${RUST_LOG:-warning}

ADD server/requirements.txt server/
RUN pip install --no-cache-dir -r server/requirements.txt

ADD --chown=indy:indy indy_config.py /etc/indy/
ADD --chown=indy:indy . $HOME
ADD --chown=indy:indy resources/gen_txn_files/pool_transactions_genesis /home/indy/ledger/sandbox/pool_transactions_genesis