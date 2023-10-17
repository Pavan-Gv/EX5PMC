# EX5PMC
```c
#include "main.h"
#include "lcd.h"
#include "stdbool.h"

bool col1,col2,col3,col4;

void SystemClock_Config(void);
static void MX_GPIO_Init(void);

void key();



int main(void)
{
  HAL_Init();
  SystemClock_Config();
  MX_GPIO_Init();
  while (1)
  {
    key();
    HAL_Delay(1000);
  }
}
void key()
{
	Lcd_PortType ports[] = {GPIOA,GPIOA,GPIOA,GPIOA};
	Lcd_PinType pins[] = {GPIO_PIN_3,GPIO_PIN_2,GPIO_PIN_1,GPIO_PIN_0};
	Lcd_HandleTypeDef lcd;
	lcd = Lcd_create(ports,pins,GPIOB,GPIO_PIN_0,GPIOB,GPIO_PIN_1,LCD_4_BIT_MODE);

	HAL_GPIO_WritePin(GPIOC, GPIO_PIN_0, GPIO_PIN_RESET);
	HAL_GPIO_WritePin(GPIOC, GPIO_PIN_1, GPIO_PIN_SET);
	HAL_GPIO_WritePin(GPIOC, GPIO_PIN_2, GPIO_PIN_SET);
	HAL_GPIO_WritePin(GPIOC, GPIO_PIN_3, GPIO_PIN_SET);

	col1 = HAL_GPIO_ReadPin(GPIOC, GPIO_PIN_4);
	col2 = HAL_GPIO_ReadPin(GPIOC, GPIO_PIN_5);
	col3 = HAL_GPIO_ReadPin(GPIOC, GPIO_PIN_6);
	col4 = HAL_GPIO_ReadPin(GPIOC, GPIO_PIN_7);

	if(!col1){
		Lcd_cursor(&lcd,0,1);
		Lcd_string(&lcd,"key 7\n");
		HAL_Delay(500);
		col1=1;
	}
	else if(!col2){
		Lcd_cursor(&lcd,0,1);
		Lcd_string(&lcd,"key 8\n");
		HAL_Delay(500);
		col2=1;
		}
	else if(!col3){
		Lcd_cursor(&lcd,0,1);
		Lcd_string(&lcd,"key 9\n");
		HAL_Delay(500);
		col3=1;
	}
	else if(!col4){
		Lcd_cursor(&lcd,0,1);
		Lcd_string(&lcd,"key %\n");
		HAL_Delay(500);
		col4=1;
	}


	HAL_GPIO_WritePin(GPIOC, GPIO_PIN_0, GPIO_PIN_SET);
	HAL_GPIO_WritePin(GPIOC, GPIO_PIN_1, GPIO_PIN_RESET);
	HAL_GPIO_WritePin(GPIOC, GPIO_PIN_2, GPIO_PIN_SET);
	HAL_GPIO_WritePin(GPIOC, GPIO_PIN_3, GPIO_PIN_SET);

	col1 = HAL_GPIO_ReadPin(GPIOC, GPIO_PIN_4);
	col2 = HAL_GPIO_ReadPin(GPIOC, GPIO_PIN_5);
	col3 = HAL_GPIO_ReadPin(GPIOC, GPIO_PIN_6);
	col4 = HAL_GPIO_ReadPin(GPIOC, GPIO_PIN_7);

	if(!col1){
		Lcd_cursor(&lcd,0,1);
		Lcd_string(&lcd,"key 4\n");
		HAL_Delay(500);
		col1=1;
	}
	else if(!col2){
		Lcd_cursor(&lcd,0,1);
		Lcd_string(&lcd,"key 5\n");
		HAL_Delay(500);
		col2=1;
		}
	else if(!col3){
		Lcd_cursor(&lcd,0,1);
		Lcd_string(&lcd,"key 6\n");
		HAL_Delay(500);
		col3=1;
	}
	else if(!col4){
		Lcd_cursor(&lcd,0,1);
		Lcd_string(&lcd,"key *\n");
		HAL_Delay(500);
		col4=1;
	}


	HAL_GPIO_WritePin(GPIOC, GPIO_PIN_0, GPIO_PIN_SET);
	HAL_GPIO_WritePin(GPIOC, GPIO_PIN_1, GPIO_PIN_SET);
	HAL_GPIO_WritePin(GPIOC, GPIO_PIN_2, GPIO_PIN_RESET);
	HAL_GPIO_WritePin(GPIOC, GPIO_PIN_3, GPIO_PIN_SET);

	col1 = HAL_GPIO_ReadPin(GPIOC, GPIO_PIN_4);
	col2 = HAL_GPIO_ReadPin(GPIOC, GPIO_PIN_5);
	col3 = HAL_GPIO_ReadPin(GPIOC, GPIO_PIN_6);
	col4 = HAL_GPIO_ReadPin(GPIOC, GPIO_PIN_7);

	if(!col1){
		Lcd_cursor(&lcd,0,1);
		Lcd_string(&lcd,"key 1\n");
		HAL_Delay(500);
		col1=1;
	}
	else if(!col2){
		Lcd_cursor(&lcd,0,1);
		Lcd_string(&lcd,"key 2\n");
		HAL_Delay(500);
		col2=1;
		}
	else if(!col3){
		Lcd_cursor(&lcd,0,1);
		Lcd_string(&lcd,"key 3\n");
		HAL_Delay(500);
		col3=1;
	}
	else if(!col4){
		Lcd_cursor(&lcd,0,1);
		Lcd_string(&lcd,"key -\n");
		HAL_Delay(500);
		col4=1;
	}

	HAL_GPIO_WritePin(GPIOC, GPIO_PIN_0, GPIO_PIN_SET);
	HAL_GPIO_WritePin(GPIOC, GPIO_PIN_1, GPIO_PIN_SET);
	HAL_GPIO_WritePin(GPIOC, GPIO_PIN_2, GPIO_PIN_SET);
	HAL_GPIO_WritePin(GPIOC, GPIO_PIN_3, GPIO_PIN_RESET);

	col1 = HAL_GPIO_ReadPin(GPIOC, GPIO_PIN_4);
	col2 = HAL_GPIO_ReadPin(GPIOC, GPIO_PIN_5);
	col3 = HAL_GPIO_ReadPin(GPIOC, GPIO_PIN_6);
	col4 = HAL_GPIO_ReadPin(GPIOC, GPIO_PIN_7);

	if(!col1){
		Lcd_cursor(&lcd,0,1);
		Lcd_string(&lcd,"key ON/C\n");
		HAL_Delay(500);
		col1=1;
	}
	else if(!col2){
		Lcd_cursor(&lcd,0,1);
		Lcd_string(&lcd,"key 0\n");
		HAL_Delay(500);
		col2=1;
		}
	else if(!col3){
		Lcd_cursor(&lcd,0,1);
		Lcd_string(&lcd,"key =\n");
		HAL_Delay(500);
		col3=1;
	}
	else if(!col4){
		Lcd_cursor(&lcd,0,1);
		Lcd_string(&lcd,"key +\n");
		HAL_Delay(500);
		col4=1;
	}
}
```
