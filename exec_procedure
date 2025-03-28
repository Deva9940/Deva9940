import pyodbc



from datetime import datetime

# Database Connection Parameters

SERVER = "sma.ctzt1q0dkfdj.us-east-1.rds.amazonaws.com"

DATABASE = "EC_SMADealerPortal"

USERNAME = "dealerportalsma"

PASSWORD = "ejadmin123"

STORED_PROCEDURE = "shopify.pricesync"

def execute_stored_procedure():

    """Connects to SQL Server and executes the stored procedure."""

    try:

        # Establish connection

        conn = pyodbc.connect(

            f"DRIVER={{SQL Server}};SERVER={SERVER};DATABASE={DATABASE};UID={USERNAME};PWD={PASSWORD}"

        )

        cursor = conn.cursor()

        # Execute the stored procedure

        print(f"[{datetime.now()}] Executing stored procedure: {STORED_PROCEDURE}")

        cursor.execute(f"EXEC {STORED_PROCEDURE}")

        # Commit and close connection

        conn.commit()

        cursor.close()

        conn.close()

        print(f"[{datetime.now()}] Execution completed successfully!")

    except Exception as e:

        print(f"[{datetime.now()}] Error executing stored procedure: {e}")



execute_stored_procedure()
