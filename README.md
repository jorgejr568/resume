# Jorge Junior

---
> Sou um programador backend e frontend. Trabalho com desenvolvimento de aplicações web, sistemas para web, websites e blogs. No momento trabalho com Laravel e Vue.js. Estudante de ciência da computação, apaixonado por programação e amante de desafios.

---
```php
<?php

namespace Life\JorgeJunior;

class Resume
{
	/**
	 * Status de relacionamento
	 *
	 * @var bool
	 */
	protected $relationship = false;

	/**
	 * Data de nascimento
	 *
	 * @var string
	 */
	protected $birth = '1998-04-27';

	/**
	 * Minha idade
	 *
	 * @var string
	 */
	 protected $years;

	/**
	 * Empresas para as quais trabalhei
	 *
	 * @var array
	 */
	protected $companies = [
		[
			'name' => 'Hostnet Internet',
			'function' => 'Desenvolvedor de ferramentas para o setor de suporte',
			'start' => '2015-05',
			'end' => '2016-06'
		],
		[
			'name' => 'Freelancer, Autônomo',
			'function' => 'Desenvolvedor Web e projetista de banco de dados',
			'start' => '2016-02',
			'end' => 'now'
		],
		[
			'name' => 'Centro Federal de Educação Tecnológica Celso Suckow da Fonseca',
			'function' => 'Bolsista de extensão',
			'start' => '2017-04',
			'end' => 'now'
		]
	];

	/**
	 * Minhas habilidades e competências.
	 *
	 * @var array
	 */
	protected $skills = [
		'master' => [
			'PHP',
			'HTML5',
			'Javascript',
			'SASS',
			'jQuery',
			'Laravel',
      			'Bootstrap'
		],
		'large' => [
			'Zend Framework 3',
			'API RESTfull',
      			'Sistemas para Web'
		],
		'medium' => [
			'CSS3',
			'Vue.js',
			'Estrutura MVC',
		],
		'basic' => [
			'Photoshop e GIMP',
			'GULP',
			'NodeJS',
			'Express.js'
		]
	];

	/**
	 * Efetue ao iniciar
	 *
	 */
	public function __construct()
	{
		$this->years = $this->getYears( $this->birth, date('Y-m-d'), '%y' );
		$this->companies = $this->getCompaniesThatWorked( $this->companies );
	}

	/**
	 * Tratamento do intervalo de datas.
	 *
	 * @var string|string|string
	 * @return string
	 */
	public function getYears( $start, $end, $type = '%y ano(s), %m mes(s)' )
	{
		$primary = date_create( $start );
		$secondary = date_create( $end );
		$interval = date_diff($primary, $secondary);

		return $interval->format($type);
	}

	/**
	 * Tratamento das datas das empresas nas quais eu trabalhei.
	 *
	 * @var array
	 * @return array
	 */
	public function getCompaniesThatWorked( $companies )
	{
		if( is_array( $companies ) )
		{
			foreach( $companies as $company )
			{
				$transform[] = [
					'name' => $company[ 'name' ],
					'function' => $company[ 'function' ],
					'start' => $company[ 'start' ],
					'end' => $company[ 'end' ],
					'total' => $this->getYears( $company['start'], $company['end'])
				];
			}
		}

		return (isset( $transform ) ? $transform : null);
	}
}

```
---
> "É ótimo celebrar o sucesso, mas mais importante ainda é assimilar as lições trazidas pelos erros que cometemos".
Jorge Junior - contato@jorgejuniorx.com.br  
Telefone: +55 21 98004-9107
**Skype**: jorge.junior.568@live.com
