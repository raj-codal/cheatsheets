# MYSQL CHEATSHEET



# STORED PROCEDURE BODY WITH CONDITIONAL IF THEN STATEMENT

BEGIN
INSERT INTO stock
    (`code`,`amount`,`supplier`)
VALUES
    (code1,amount1, supplier1)
ON DUPLICATE KEY UPDATE
	amount = amount + amount1;

INSERT INTO `stock_transactions`(`price`, `supplier`, `code`) VALUES (price1, supplier1, code1);
SET @ID = LAST_INSERT_ID();
SELECT @ID;

IF debug_mode = true THEN
	INSERT INTO `monitor`(`id_in_table`,`table_name`,`data`) VALUES 		(code1, "stock", "OK");
    INSERT INTO `monitor`(`id_in_table`,`table_name`,`data`) VALUES 		(@ID, "stock_transactions", "OK");
END IF;

END
