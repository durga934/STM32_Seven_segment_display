# STM32_Seven_segment_display
#define RCCAPB2ENR *((volatile uint32_t*)0x40021018)
#define GPIOA_CRL *((volatile uint32_t*)0x40010800)
#define GPIOA_CRH *((volatile uint32_t*)0x40010804)
#define GPIOA_ODR *((volatile uint32_t*)0x4001080C)
void delay();
int main()
{
	RCC |= (1<<2);
	GPIOA_CRL |= 0x22222222;
	GPIOA_CRH |= 0x22222222;

	while(1)
	{
		GPIOA_ODR |=0X0E06;
		delay();
		GPIOA_ODR |=0X0D5B;
		delay();
		GPIOA_ODR |=0X0F2D;
		delay();
		GPIOA_ODR |=0X066E;
		delay();
	}

}
void delay()
	{
		for(int i=0;i<5000;i++);
	}
