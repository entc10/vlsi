LIBRARY IEEE;
USE IEEE.STD_LOGIC_1164.ALL;
USE IEEE.NUMERIC_STD.ALL;

ENTITY keypad IS
    PORT (
        clk       : IN  STD_LOGIC;
        rst       : IN  STD_LOGIC;
        Row       : OUT STD_LOGIC_VECTOR(3 DOWNTO 0);
        Col       : IN  STD_LOGIC_VECTOR(3 DOWNTO 0);
        Key_code  : OUT STD_LOGIC_VECTOR(3 DOWNTO 0);
        Key_valid : OUT STD_LOGIC
    );
END keypad;

ARCHITECTURE Behavioral OF keypad IS

    SIGNAL state : INTEGER RANGE 0 TO 3 := 0;

BEGIN

    PROCESS(clk, rst)
    BEGIN

        IF rst = '1' THEN

            Row       <= "1111";
            Key_code  <= "0000";
            Key_valid <= '0';
            state     <= 0;

        ELSIF rising_edge(clk) THEN

            Key_valid <= '0';

            CASE state IS

                WHEN 0 =>
                    Row <= "1110";

                    IF Col(0) = '0' THEN
                        Key_code <= "0000";
                        Key_valid <= '1';
                    ELSIF Col(1) = '0' THEN
                        Key_code <= "0001";
                        Key_valid <= '1';
                    ELSIF Col(2) = '0' THEN
                        Key_code <= "0010";
                        Key_valid <= '1';
                    ELSIF Col(3) = '0' THEN
                        Key_code <= "0011";
                        Key_valid <= '1';
                    END IF;

                    state <= 1;

                WHEN 1 =>
                    Row <= "1101";

                    IF Col(0) = '0' THEN
                        Key_code <= "0100";
                        Key_valid <= '1';
                    ELSIF Col(1) = '0' THEN
                        Key_code <= "0101";
                        Key_valid <= '1';
                    ELSIF Col(2) = '0' THEN
                        Key_code <= "0110";
                        Key_valid <= '1';
                    ELSIF Col(3) = '0' THEN
                        Key_code <= "0111";
                        Key_valid <= '1';
                    END IF;

                    state <= 2;

                WHEN 2 =>
                    Row <= "1011";

                    IF Col(0) = '0' THEN
                        Key_code <= "1000";
                        Key_valid <= '1';
                    ELSIF Col(1) = '0' THEN
                        Key_code <= "1001";
                        Key_valid <= '1';
                    ELSIF Col(2) = '0' THEN
                        Key_code <= "1010";
                        Key_valid <= '1';
                    ELSIF Col(3) = '0' THEN
                        Key_code <= "1011";
                        Key_valid <= '1';
                    END IF;

                    state <= 3;

                WHEN 3 =>
                    Row <= "0111";

                    IF Col(0) = '0' THEN
                        Key_code <= "1100";
                        Key_valid <= '1';
                    ELSIF Col(1) = '0' THEN
                        Key_code <= "1101";
                        Key_valid <= '1';
                    ELSIF Col(2) = '0' THEN
                        Key_code <= "1110";
                        Key_valid <= '1';
                    ELSIF Col(3) = '0' THEN
                        Key_code <= "1111";
                        Key_valid <= '1';
                    END IF;

                    state <= 0;

                WHEN OTHERS =>
                    state <= 0;

            END CASE;

        END IF;

    END PROCESS;

END Behavioral;
